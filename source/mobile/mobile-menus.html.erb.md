---
title: "Related Tips and Techniques: Mobile Menus"
order: 4
status: editors-draft
wcag_success_criteria:
editors:
  - Kim Patch
  - Kathy Wahlbin
  - Judy Brewer
contributors:
  - The Education and Outreach Working Group (<a href="https://www.w3.org/WAI/EO/">EOWG</a>)
support: Developed with support from the <a href="https://www.w3.org/WAI/WCAGTA/">U.S. Access Board, WCAG TA Project</a>
---

In mobile navigation a single button is often used to expand and collapse a set of navigation links. When the button is activated, a menu appears visually adjacent to the button. It’s also important to ensure that the expanded content is easily discoverable by keyboard-only and screen reader users.

## Step 1: Create a Button to Display and Hide the Menu

For the control to show and hide the menu, use a button with a valid name.

{::nomarkdown}
<%= code_start('', 'HTML') %>
{:/nomarkdown}

~~~html
<button id="menuButton" class="icon"><img src="menu.png" alt="Menu"></button>
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}

## Step 2: Convey the State of the Menu

There are multiple ways to describe whether the menu is expanded or collapsed. The aria-expanded attribute conveys this information to assistive technology users.

{::nomarkdown}
<%= code_start('', 'HTML') %>
{:/nomarkdown}

~~~html
<button id="menuButton" class="icon" aria-expanded="false"><img src="menu.png" alt="Menu"></button>
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}

## Step 3: Make the Menu Contents Discoverable

When the menu is open, users should be able to easily discover the new content. Two techniques can be used to aid discovery.

1. The `aria-controls` attribute

   This attribute semantically ties the button to the area it controls. Assistive technologies that support the attribute will allow users to jump straight to this area.

2. Menu placement

   To make the new content easily discoverable for assistive technologies that don’t support aria-controls, place the menu contents immediately after the button. This allows screen reader users and keyboard-only users to find the new content when they navigate to the next item in the page.

{::nomarkdown}
<%= code_start('', 'HTML') %>
{:/nomarkdown}

~~~html
<button id="menuButton" class="icon" aria-expanded="false" aria-controls="menuItems"><img src="menu.png" alt="Menu"></button>
<ul id="menuItems">
  <li><a href="#home">Home</a></li>
  <li><a href="#products">Products</a></li>
  <li><a href="#about">About Us</a></li>
</ul>
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}


##Step 4: Define the Entire Menu as a Navigational Area

To describe the function of the entire menu system, wrap the entire structure with a navigation element that contains a label describing its function.

Make the expanded menu the next item in the DOM after the button that expands and collapses it. On the button that controls the menu’s visibility, use aria-expanded to indicate if the menu is expanded and use aria-controls to point to the expanded content.

{::nomarkdown}
<%= code_start('', 'HTML') %>
{:/nomarkdown}

~~~html
<nav class='navTopLevel closed' id='mainNav' aria-label="Main">
<button id="menuButton" class="icon" aria-expanded="false" aria-controls="menuItems"><img src="menu.png" alt="Menu"></button>
<ul id="menuItems">
  <li><a href="#home">Home</a></li>
  <li><a href="#products">Products</a></li>
  <li><a href="#about">About Us</a></li>
</ul>
</nav>
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}

##Complete Source Code

{::nomarkdown}
<%= code_start('', 'HTML') %>
{:/nomarkdown}

~~~html
<p class="siteName">Responsive Menu Demo</p>
<nav class='navTopLevel closed' id='mainNav' aria-label="Main">
<button id="menuButton" class="icon" aria-expanded="false" aria-controls="menuItems"><img src="menu.png" alt="Menu"></button>
<ul id="menuItems">
  <li><a href="#home">Home</a></li>
  <li><a href="#products">Products</a></li>
  <li><a href="#about">About Us</a></li>
</ul>
</nav>

<h1>Responsive menu example</h1>
<p>This is where the main page text goes.</p>
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}

{::nomarkdown}
<%= code_start('', 'CSS') %>
{:/nomarkdown}

~~~css
.navTopLevel a {
    color: #f2f2f2;
    padding: 1em;
    text-decoration: none;
    font-size: 1em;
}

.navTopLevel a:hover, .navTopLevel a:focus {
    background-color: #ddd;
    color: #000;
}

.navTopLevel ul {
  list-style: none;
  background-color: #333;
  padding-left:0;
}

.navTopLevel ul li {
  margin-left:0;
}

.opened ul {
  display:block;
  position: absolute;
  z-index:1;
  width:75%;
}

.closed ul{
  display:none;
}

.navTopLevel .icon {

}

.navTopLevel.opened a {
  display: block;
  text-align: left;
}

.navTopLevel button {
  background-color: #fff;
  height:52px;
  width:62px;
  padding:0;
  border:none;
}

.siteName {
  font-size:1.2em;
  font-weight:bold;
}

@media screen and (min-width: 600px) {

  .navTopLevel button.icon {
      display: none;
  }
  .navTopLevel li {
    display:inline-block;
    height:2em;
    margin-top:1em;
    line-height:1em;
  }

  .closed ul, .opened ul{
    display: inherit;
  }
}
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}

{::nomarkdown}
<%= code_start('', 'JavaScript') %>
{:/nomarkdown}

~~~js
function toggleMenu(event) {
  var navBar = document.getElementById("mainNav");
  var expanded = event.currentTarget.getAttribute("aria-expanded");
  if (expanded==="true") {
    navBar.classList.add("closed");
    navBar.classList.remove("opened");
    event.currentTarget.setAttribute('aria-expanded', 'false');
    event.currentTarget.firstChild.setAttribute('src','menu.png');
  } else {
    navBar.classList.add("opened");
    navBar.classList.remove("closed");
    event.currentTarget.setAttribute('aria-expanded', 'true');
    event.currentTarget.firstChild.setAttribute('src','menu-active.png');
  }

}

document.getElementById('menuButton').addEventListener('click', toggleMenu, false);
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}