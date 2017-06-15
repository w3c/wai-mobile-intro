---
title: "Related Tips and Techniques: Mobile Form Labels"
order: 3
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

Form layout can be challenging when screen space is at a minimum. A horizontal layout with adjacent label and form makes the form fields difficult to work with because the text is so small. And if you zoom in to see the form input, the label might not be visible on the screen, making it more difficult to complete the form.

## Vertically Stacked Forms
{:.ap}

Positioning labels above each form element allows both the label and the form element to be visible at the same time. Make sure there is enough spacing between every form element that it is clear which label belongs with each form element.

{::nomarkdown}
<%= code_start('', 'HTML') %>
{:/nomarkdown}

~~~html
<div class="field">
  <label for="first">First Name</label>
  <input id="first" type="text">
 </div>

<div class="field">
  <label for="middle">Middle Name</label>
  <input id="middle" type="text">
</div>

<div class="field">
  <label for="last">Last Name</label>
  <input id="last" type="text">
</div>
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}

{::nomarkdown}
<%= code_start('', 'CSS') %>
{:/nomarkdown}

~~~css
.field {
  margin-bottom:2em;
}

.field input {
  display:block;
}

.field label {
  display:block;
}
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}

## Vertically Stacked Forms with Floating Labels
{:.ap}

It’s popular to minimize the space required for form fields by using placeholder attributes to provide visual labels for the form elements. But the placeholder text goes away after text has been entered, so the "label" is no longer presented visually to the user. This makes it difficult to review entries on a form to ensure they’re correct.

Here’s a different approach that’s more accessible. The label element can be positioned where the placeholder text would normally be positioned. Once a form field receives focus, or when text is entered, the label is repositioned above the form element so the label is still available visually and programmatically.

{::nomarkdown}
<%= code_start('', 'HTML') %>
{:/nomarkdown}

~~~html
<div class="field">
  <label for="first">First Name</label>
  <input id="first" type="text">
 </div>

<div class="field">
  <label for="middle">Middle Name</label>
  <input id="middle" type="text">
</div>

<div class="field">
  <label for="last">Last Name</label>
  <input id="last" type="text">
</div>
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}

{::nomarkdown}
<%= code_start('', 'CSS') %>
{:/nomarkdown}

~~~css
.field {
  position:relative;
  margin-bottom:1em;
}

.field input {
  font-size:1em;
  padding-top:.75em;
  padding-bottom:.75em;
  padding-left:0.5em;
}

.field.hasContent input {
  padding-top: 1.25em;
  padding-bottom:.25em;
}

.field label {
  position: absolute;
  top: 1em;
  left: 1em;
  color: #666666;
  font-size:1em;
  transition: top .2s, left .2s;
}
.field.hasContent label {
  top:.25em;
  left:.375em;
  color:#000;
  font-size: 0.8em;
  font-weight:bold;
  transition: top .2s ease-out, left .2s;
}
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}

{::nomarkdown}
<%= code_start('', 'JavaScript') %>
{:/nomarkdown}

~~~js
var floatingLabelFocus = function() {
    this.parentNode.classList.add("hasContent");
};

var floatingLabelBlur = function() {
  if(this.value.length > 0){
    this.parentNode.classList.add("hasContent");
  } else {
    this.parentNode.classList.remove("hasContent");
  }
};

var classname = document.getElementsByClassName("field");

for (var i = 0; i < classname.length; i++) {
  var el = classname[i].getElementsByTagName("input")[0];
  if(el.value.length > 0){
    el.parentNode.classList.add("hasContent");
  }
   el.addEventListener('focus', floatingLabelFocus, false);
   el.addEventListener('blur', floatingLabelBlur, false);
}
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}
