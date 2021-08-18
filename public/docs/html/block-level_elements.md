Block-level elements
====================

HTML (**Hypertext Markup Language**) elements historically were categorized as either "block-level" elements or "inline-level" elements. Since this is a presentational characteristic it is nowadays specified by CSS in the [Flow Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flow_Layout). A Block-level element occupies the entire horizontal space of its parent element (container), and vertical space equal to the height of its contents, thereby creating a "block". In this article, we'll examine HTML block-level elements and how they differ from [inline-level elements](inline_elements).

Browsers typically display the block-level element with a newline both before and after the element. You can visualize them as a stack of boxes.

A block-level element always starts on a new line and takes up the full width available (stretches out to the left and right as far as it can).

The following example demonstrates the block-level element's influence:

Block-level elements
--------------------

### HTML

    <p>This paragraph is a block-level element; its background has been colored to display the paragraph's parent element.</p>

### CSS

    p { background-color: #8ABB55; }

Usage
-----

-   Block-level elements may appear only within a [`<body>`](element/body) element.

Block-level vs. inline
----------------------

There are a couple of key differences between block-level elements and inline elements:

Content model  
Generally, block-level elements may contain inline elements and (sometimes) other block-level elements. Inherent in this structural distinction is the idea that block elements create "larger" structures than inline elements.

Default formatting  
By default, block-level elements begin on new lines, but inline elements can start anywhere in a line.

The distinction of block-level vs. inline elements was used in HTML specifications up to 4.01. In HTML5, this binary distinction is replaced with a more complex set of [content categories](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories). While the "inline" category roughly corresponds to the category of [phrasing content](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content), the "block-level" category doesn't directly correspond to any HTML5 content category, but *"block-level" and "inline" elements combined together* correspond to the [flow content](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content) in HTML5. There are also additional categories, e.g. [interactive content](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#interactive_content).

Elements
--------

The following is a complete list of all HTML "block-level" elements (although "block-level" is not technically defined for elements that are new in HTML5).

[`<address>`](element/address)  
Contact information.

[`<article>`](element/article)  
Article content.

[`<aside>`](element/aside)  
Aside content.

[`<blockquote>`](element/blockquote)  
Long ("block") quotation.

[`<details>`](element/details)  
Disclosure widget.

[`<dialog>`](element/dialog)  
Dialog box.

[`<dd>`](element/dd)  
Describes a term in a description list.

[`<div>`](element/div)  
Document division.

[`<dl>`](element/dl)  
Description list.

[`<dt>`](element/dt)  
Description list term.

[`<fieldset>`](element/fieldset)  
Field set label.

[`<figcaption>`](element/figcaption)  
Figure caption.

[`<figure>`](element/figure)  
Groups media content with a caption (see [`<figcaption>`](element/figcaption)).

[`<footer>`](element/footer)  
Section or page footer.

[`<form>`](element/form)  
Input form.

 [`<h1>`](element/heading_elements), [`<h2>`](element/heading_elements), [`<h3>`](element/heading_elements), [`<h4>`](element/heading_elements), [`<h5>`](element/heading_elements), [`<h6>`](element/heading_elements)   
Heading levels 1-6.

[`<header>`](element/header)  
Section or page header.

[`<hgroup>`](element/hgroup)  
Groups header information.

[`<hr>`](element/hr)  
Horizontal rule (dividing line).

[`<li>`](element/li)  
List item.

[`<main>`](element/main)  
Contains the central content unique to this document.

[`<nav>`](element/nav)  
Contains navigation links.

[`<ol>`](element/ol)  
Ordered list.

[`<p>`](element/p)  
Paragraph.

[`<pre>`](element/pre)  
Preformatted text.

[`<section>`](element/section)  
Section of a web page.

[`<table>`](element/table)  
Table.

[`<ul>`](element/ul)  
Unordered list.

See also
--------

-   [Inline elements](inline_elements)
-   [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
-   [Block and Inline Layout in Normal Flow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flow_Layout/Block_and_Inline_Layout_in_Normal_Flow)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements</a>
