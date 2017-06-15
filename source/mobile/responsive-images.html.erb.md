---
title: "Related Tips and Techniques: Responsive Images"
order: 5
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

High resolution images are often not needed for the smaller viewports of small devices. Image size can be made responsive by using the same "container" for the image in all the viewport sizes, but changing out the image source file. There are two techniques for doing this. In both cases all images must be adequately described using the same principles for [describing images](https://www.w3.org/WAI/tutorials/images/).

##Technique 1: The `<picture>` Element

The picture element can be used to describe image sources. The `<picture>` element needs a base image using the `<img>` element, which is enabled with alternative text. No matter what `<source>` is used in the `<picture>` is used, the same alt attribute is used.

{::nomarkdown}
<%= code_start('', 'HTML') %>
{:/nomarkdown}

~~~html
<picture>
  <source media="(max-width: 40em)"
    srcset="dragon-320.jpg 1x">
  <source media="(max-width: 80em)"
    srcset="dragon-640.jpg 1x">
  <source
    srcset="dragon-1024.jpg 1x">
  <img src="dragon-640.jpg" alt="60 foot long dragon lit internally with lights">
</picture>
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}


##Technique 2: The srcset Attribute
A similar approach is to use a single <img> element, but use the srcset attribute to define image sources for different viewports. The <img> element space is enabled with alternative text.

{::nomarkdown}
<%= code_start('', 'HTML') %>
{:/nomarkdown}

~~~html
<img src="dragon-640.jpg"
        srcset="dragon-1024.jpg 1024w, dragon-640.jpg 640w, dragon-320.jpg 320w"
        sizes="(min-width: 320px) 33.3vw, 100vw"
        alt="60 foot long dragon lit internally with lights"
>
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}


Figure 1: Dragon 320.jpg

Figure 2: Dragon 640.jpg

Figure 3: Dragon 1024.jpg
