---
title: "Related Tips and Techniques: Responsive Data Tables"
order: 6
status: editors-draft
wcag_success_criteria:
wcag_techniques:
editors:
  - Kim Patch
  - Kathy Wahlbin
  - Judy Brewer
contributors:
  - The Education and Outreach Working Group (<a href="https://www.w3.org/WAI/EO/">EOWG</a>)
support: Developed with support from the <a href="https://www.w3.org/WAI/WCAGTA/">U.S. Access Board, WCAG TA Project</a>

---

Creating a table that works in both a desktop and mobile view is challenging. The fundamental problem is a data table of any significant size is designed to work well on larger screens. This is especially noticeable with more than just a few columns.

When wide tables are made to visually fit into a smaller screen, a table’s  contents often become either too small to read without zooming in, or the table requires scrolling. Scrolling introduces one of two problems on small screens. If the row and column headers scroll out of view, it’s hard for users to remember what information they’re looking at; if headers are fixed and just the data portion scrolls, the interaction is unfamiliar to users, and it is difficult for developers to make a scrollable table with fixed headers that works on all mobile platforms and is accessible to all assistive technologies, especially screen readers.

For many tables, it’s better to redesign the way the data is presented for mobile views. The most logical transformation is to use a nested list instead of a table. One set of table headers becomes the first level list items, the other set of table headers along with the data cells becomes a nested list, and the caption for the table becomes the heading for the list. In this model, there are two separate data structures – a list and a table – but only one is visible on the screen at a time.

## Responsive data table – large screen view

{::nomarkdown}
<%= sample_start('', 'Large screen view') %>
{:/nomarkdown}

<table id="desktop-table">
  <caption>Delivery slots:</caption>
  <tbody>
    <tr>
      <td></td>
      <th scope="col">Monday</th>
      <th scope="col">Tuesday</th>
      <th scope="col">Wednesday</th>
      <th scope="col">Thursday</th>
      <th scope="col">Friday</th>
    </tr>
    <tr>
      <th scope="row">09:00 - 11:00</th>
      <td>Closed</td>
      <td>Open</td>
      <td>Open</td>
      <td>Closed</td>
      <td>Closed</td>
    </tr>
    <tr>
      <th scope="row">11:00 - 13:00</th>
      <td>Open</td>
      <td>Open</td>
      <td>Closed</td>
      <td>Closed</td>
      <td>Closed</td>
    </tr>
    <tr>
      <th scope="row">13:00 - 15:00</th>
      <td>Open</td>
      <td>Open</td>
      <td>Open</td>
      <td>Closed</td>
      <td>Closed</td>
    </tr>
    <tr>
      <th scope="row">15:00 - 17:00</th>
      <td>Closed</td>
      <td>Closed</td>
      <td>Closed</td>
      <td>Open</td>
      <td>Open</td>
    </tr>
  </tbody>
</table>

{::nomarkdown}
<%= sample_end %>
{:/nomarkdown}

{::nomarkdown}
<%= code_start('', 'HTML') %>
{:/nomarkdown}

~~~html
<table id="desktop-table">
  <caption>Delivery slots:</caption>
  <tbody>
    <tr>
      <td></td>
      <th scope="col">Monday</th>
      <th scope="col">Tuesday</th>
      <th scope="col">Wednesday</th>
      <th scope="col">Thursday</th>
      <th scope="col">Friday</th>
    </tr>
    <tr>
      <th scope="row">09:00 - 11:00</th>
      <td>Closed</td>
      <td>Open</td>
      <td>Open</td>
      <td>Closed</td>
      <td>Closed</td>
    </tr>
    <tr>
      <th scope="row">11:00 - 13:00</th>
      <td>Open</td>
      <td>Open</td>
      <td>Closed</td>
      <td>Closed</td>
      <td>Closed</td>
    </tr>
    <tr>
      <th scope="row">13:00 - 15:00</th>
      <td>Open</td>
      <td>Open</td>
      <td>Open</td>
      <td>Closed</td>
      <td>Closed</td>
    </tr>
    <tr>
      <th scope="row">15:00 - 17:00</th>
      <td>Closed</td>
      <td>Closed</td>
      <td>Closed</td>
      <td>Open</td>
      <td>Open</td>
    </tr>
  </tbody>
</table>
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}

## Responsive data table – small screen view

{::nomarkdown}
<%= sample_start('', 'Small Screen View') %>
{:/nomarkdown}

<div id="mobile-list">
  <h2>Delivery Slots</h2>
  <ul>
    <li>Monday
      <ul>
        <li>09:00 - 11:00 Closed</li>
        <li>11:00 - 13:00 Open</li>
        <li>13:00 - 15:00 Open</li>
        <li>15:00 - 17:00 Closed</li>
      </ul>
    </li>
    <li>Tuesday
      <ul>
        <li>09:00 - 11:00 Open</li>
        <li>11:00 - 13:00 Open</li>
        <li>13:00 - 15:00 Open</li>
        <li>15:00 - 17:00 Closed</li>
      </ul>
    </li>
    <li>Wednesday
      <ul>
        <li>09:00 - 11:00 Open</li>
        <li>11:00 - 13:00 Closed</li>
        <li>13:00 - 15:00 Open</li>
        <li>15:00 - 17:00 Closed</li>
      </ul>
    </li>
    <li>Thursday
      <ul>
        <li>09:00 - 11:00 Closed</li>
        <li>11:00 - 13:00 Closed</li>
        <li>13:00 - 15:00 Closed</li>
        <li>15:00 - 17:00 Open</li>
      </ul>
    </li>
    <li>Friday
      <ul>
        <li>09:00 - 11:00 Closed</li>
        <li>11:00 - 13:00 Closed</li>
        <li>13:00 - 15:00 Closed</li>
        <li>15:00 - 17:00 Open</li>
      </ul>
    </li>
  </ul>
</div>

{::nomarkdown}
<%= sample_end %>
{:/nomarkdown}

{::nomarkdown}
<%= code_start('', 'HTML') %>
{:/nomarkdown}

~~~html
<div id="mobile-list">
  <h2>Delivery Slots</h2>
  <ul>
    <li>Monday
      <ul>
        <li>09:00 - 11:00 Closed</li>
        <li>11:00 - 13:00 Open</li>
        <li>13:00 - 15:00 Open</li>
        <li>15:00 - 17:00 Closed</li>
      </ul>
    </li>
    <li>Tuesday
      <ul>
        <li>09:00 - 11:00 Open</li>
        <li>11:00 - 13:00 Open</li>
        <li>13:00 - 15:00 Open</li>
        <li>15:00 - 17:00 Closed</li>
      </ul>
    </li>
    <li>Wednesday
      <ul>
        <li>09:00 - 11:00 Open</li>
        <li>11:00 - 13:00 Closed</li>
        <li>13:00 - 15:00 Open</li>
        <li>15:00 - 17:00 Closed</li>
      </ul>
    </li>
    <li>Thursday
      <ul>
        <li>09:00 - 11:00 Closed</li>
        <li>11:00 - 13:00 Closed</li>
        <li>13:00 - 15:00 Closed</li>
        <li>15:00 - 17:00 Open</li>
      </ul>
    </li>
    <li>Friday
      <ul>
        <li>09:00 - 11:00 Closed</li>
        <li>11:00 - 13:00 Closed</li>
        <li>13:00 - 15:00 Closed</li>
        <li>15:00 - 17:00 Open</li>
      </ul>
    </li>
  </ul>
</div>
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}

##Complete Code Sample

{::nomarkdown}
<%= code_start('', 'HTML') %>
{:/nomarkdown}

~~~html
<table id="desktop-table">
  <caption>Delivery slots:</caption>
  <tbody><tr>
    <td></td>
    <th scope="col">Monday</th>
    <th scope="col">Tuesday</th>
    <th scope="col">Wednesday</th>
    <th scope="col">Thursday</th>
    <th scope="col">Friday</th>
  </tr>
  <tr>
    <th scope="row">09:00 - 11:00</th>
    <td>Closed</td>
    <td>Open</td>
    <td>Open</td>
    <td>Closed</td>
    <td>Closed</td>
  </tr>
  <tr>
    <th scope="row">11:00 - 13:00</th>
    <td>Open</td>
    <td>Open</td>
    <td>Closed</td>
    <td>Closed</td>
    <td>Closed</td>
  </tr>
  <tr>
    <th scope="row">13:00 - 15:00</th>
    <td>Open</td>
    <td>Open</td>
    <td>Open</td>
    <td>Closed</td>
    <td>Closed</td>
  </tr>
  <tr>
    <th scope="row">15:00 - 17:00</th>
    <td>Closed</td>
    <td>Closed</td>
    <td>Closed</td>
    <td>Open</td>
    <td>Open</td>
  </tr>
</tbody>

<div id="mobile-list">
  <h2>Delivery Slots</h2>
  <ul>
    <li>Monday
      <ul>
        <li>09:00 - 11:00 Closed</li>
        <li>11:00 - 13:00 Open</li>
        <li>13:00 - 15:00 Open</li>
        <li>15:00 - 17:00 Closed</li>
      </ul>
    </li>
    <li>Tuesday
      <ul>
        <li>09:00 - 11:00 Open</li>
        <li>11:00 - 13:00 Open</li>
        <li>13:00 - 15:00 Open</li>
        <li>15:00 - 17:00 Closed</li>
      </ul>
    </li>
    <li>Wednesday
      <ul>
        <li>09:00 - 11:00 Open</li>
        <li>11:00 - 13:00 Closed</li>
        <li>13:00 - 15:00 Open</li>
        <li>15:00 - 17:00 Closed</li>
      </ul>
    </li>
    <li>Thursday
      <ul>
        <li>09:00 - 11:00 Closed</li>
        <li>11:00 - 13:00 Closed</li>
        <li>13:00 - 15:00 Closed</li>
        <li>15:00 - 17:00 Open</li>
      </ul>
    </li>
    <li>Friday
      <ul>
        <li>09:00 - 11:00 Closed</li>
        <li>11:00 - 13:00 Closed</li>
        <li>13:00 - 15:00 Closed</li>
        <li>15:00 - 17:00 Open</li>
      </ul>
    </li>
  </ul>
</div>
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}


{::nomarkdown}
<%= code_start('', 'CSS') %>
{:/nomarkdown}

~~~css
#desktop-table {
    display:none;
}

#mobile-list {
    display:block;
}

#mobile-list ul {
    position: relative;
    margin-right: 20px;
}
#mobile-list ul {
  list-style-type: none;
}
#mobile-list ul li {
    font-weight:bold;
}
#mobile-list ul li ul li {
    font-weight:normal;
}

#desktop-table table, th, td {
    border:1px #000 solid;
}
#desktop-table th {
    background-color:#ccc;
}
#desktop-table th, td {
    padding: 3px;
}

@media screen and (min-width: 600px) {

    #desktop-table {
        display:block;
    }

    #mobile-list {
        display:none;
    }

}
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}
