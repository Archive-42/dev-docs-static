Inline elements
===============

HTML (**Hypertext Markup Language**) elements historically were categorized as either "block-level" elements or "inline-level" elements. Since this is a presentational characteristic it is nowadays specified by CSS in the [Flow Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flow_Layout). Inline elements are those which only occupy the space bounded by the tags defining the element, instead of breaking the flow of the content. In this article, we'll examine HTML inline-level elements and how they differ from [block-level elements](block-level_elements).

An inline element does not start on a new line and only takes up as much width as necessary.

Inline vs. block-level elements: a demonstration
------------------------------------------------

This is most easily demonstrated with a simple example. First, some simple CSS that we'll be using:

    .highlight {
      background-color:#ee3;
    }

### Inline

Let's look at the following example which demonstrates an inline element:

    <div>The following span is an <span class="highlight">inline element</span>;
    its background has been colored to display both the beginning and end of
    the inline element's influence.</div>

In this example, the [`<div>`](element/div) block-level element contains some text. Within that text is a [`<span>`](element/span) element, which is an inline element. Because the `<span>` element is inline, the paragraph correctly renders as a single, unbroken text flow, like this:

### Block-level

Now let's change that `<span>` into a block-level element, such as [`<p>`](element/p):

    <div>The following paragraph is a <p class="highlight">block-level element;</p>
    its background has been colored to display both the beginning and end of
    the block-level element's influence.</div>

Rendered using the same CSS as before, we get:

See the difference? The `<p>` element totally changes the layout of the text, splitting it into three segments: the text before the `<p>`, then the `<p>`'s text, and finally the text following the `<p>`.

### Changing element levels

You can change the *visual presentation* of an element using the CSS [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) property. For example, by changing the value of `display` from `"inline"` to `"block"`, you can tell the browser to render the inline element in a block box rather than an inline box, and vice versa. However, doing this will not change the *category* and the *content model* of the element. For example, even if the `display` of the `span` element is changed to `"block"`, it still would not allow to nest a `div` element inside it.

Conceptual differences
----------------------

In brief, here are the basic conceptual differences between inline and block-level elements:

Content model  
Generally, inline elements may contain only data and other inline elements. You can't put block elements inside inline elements.

Formatting  
By default, inline elements do not force a new line to begin in the document flow. Block elements, on the other hand, typically cause a line break to occur (although, as usual, this can be changed using CSS).

List of "inline" elements
-------------------------

The following elements are inline by default (although block and inline elements are no longer defined in HTML 5, use [content categories](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories) instead):

[`<a>`](element/a)

[`<abbr>`](element/abbr)

[`<acronym>`](element/acronym)

[`<audio>`](element/audio) (if it has visible controls)

[`<b>`](element/b)

[`<bdi>`](element/bdi)

[`<bdo>`](element/bdo)

[`<big>`](element/big)

[`<br>`](element/br)

[`<button>`](element/button)

[`<canvas>`](element/canvas)

[`<cite>`](element/cite)

[`<code>`](element/code)

[`<data>`](element/data)

[`<datalist>`](element/datalist)

[`<del>`](element/del)

[`<dfn>`](element/dfn)

[`<em>`](element/em)

[`<embed>`](element/embed)

[`<i>`](element/i)

[`<iframe>`](element/iframe)

[`<img>`](element/img)

[`<input>`](element/input)

[`<ins>`](element/ins)

[`<kbd>`](element/kbd)

[`<label>`](element/label)

[`<map>`](element/map)

[`<mark>`](element/mark)

[`<meter>`](element/meter)

[`<noscript>`](element/noscript)

[`<object>`](element/object)

[`<output>`](element/output)

[`<picture>`](element/picture)

[`<progress>`](element/progress)

[`<q>`](element/q)

[`<ruby>`](element/ruby)

[`<s>`](element/s)

[`<samp>`](element/samp)

[`<script>`](element/script)

[`<select>`](element/select)

[`<slot>`](element/slot)

[`<small>`](element/small)

[`<span>`](element/span)

[`<strong>`](element/strong)

[`<sub>`](element/sub)

[`<sup>`](element/sup)

[`<svg>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/svg)

[`<template>`](element/template)

[`<textarea>`](element/textarea)

[`<time>`](element/time)

[`<u>`](element/u)

[`<tt>`](element/tt)

[`<var>`](element/var)

[`<video>`](element/video)

[`<wbr>`](element/wbr)

See also
--------

-   [Block-level elements](block-level_elements)
-   [HTML element reference](element)
-   [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
-   [Content categories](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories)
-   [Block and Inline Layout in Normal Flow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flow_Layout/Block_and_Inline_Layout_in_Normal_Flow)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements</a>
