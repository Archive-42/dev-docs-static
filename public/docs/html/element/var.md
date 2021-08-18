&lt;var&gt;: The Variable element
=================================

The HTML **Variable element** (`<var>`) represents the name of a variable in a mathematical expression or a programming context. It's typically presented using an italicized version of the current typeface, although that behavior is browser-dependent.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

### Related elements

Other elements that are used in contexts in which `<var>` is commonly used include:

-   [`<code>`](code): The HTML Code element
-   [`<kbd>`](kbd): The HTML Keyboard input element
-   [`<samp>`](samp): The HTML Sample Output element

If you encounter code that is mistakenly using `<var>` for style purposes rather than semantic purposes, you should either use a [`<span>`](span) with appropriate CSS or, an appropriate semantic element among the following:

-   [`<em>`](em)
-   [`<i>`](i)
-   [`<q>`](q)

### Default style

Most browsers apply [`font-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style) to `"italic"` when rendering `<var>`. This can be overridden in CSS, like this:

    var {
      font: bold 15px "Courier", "Courier New", monospace;
    }

Examples
--------

### Basic example

Here's a simple example, using `<var>` to denote variable names in a mathematical equation.

    <p>A simple equation:
      <var>x</var> = <var>y</var> + 2 </p>

The output:

### Overriding the default style

Using CSS, you can override the default style for the `<var>` element. In this example, variable names are rendered using bold Courier if it's available, otherwise it falls back to the default monospace font.

#### CSS

    var {
      font: bold 15px "Courier", "Courier New", monospace;
    }

#### HTML

    <p>The variables <var>minSpeed</var> and <var>maxSpeed</var> control
       the minimum and maximum speed of the apparatus in revolutions
       per minute (RPM).</p>

This HTML uses `<var>` to enclose the names of two variables.

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-var-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;var&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-var-element">HTML5<br />
<span class="small">The definition of '&lt;var&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`var`

Yes

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/var" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/var</a>
