&lt;tt&gt;: The Teletype Text element
=====================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The obsolete **HTML Teletype Text element** (`<tt>`) creates inline text which is presented using the [user agent's](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) default monospace font face. This element was created for the purpose of rendering text as it would be displayed on a fixed-width display such as a teletype, text-only screen, or line printer.

The terms **non-proportional**, **monotype**, and **monospace** are used interchangeably and have the same general meaning: they describe a typeface whose characters are all the same number of pixels wide.

This element is obsolete, however. You should use the more semantically helpful [`<code>`](code), [`<kbd>`](kbd), [`<samp>`](samp), or [`<var>`](var) elements for inline text that needs to be presented in monospace type, or the [`<pre>`](pre) tag for content that should be presented as a separate block.

If none of the semantic elements are appropriate for your use case (for example, if you need to show some content in a non-proportional font), you should consider using the [`<span>`](span) element, styling it as desired using CSS. The [`font-family`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family) property is a good place to start.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="even"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes)

Examples
--------

### Basic example

This example uses `<tt>` to show text entered into, and output by, a terminal application.

    <p>Enter the following at the telnet command prompt: <code>set localecho</code><br />

    The telnet client should display: <tt>Local Echo is on</tt></p>

#### Result

### Overriding the default font

You can override the browser's default font—if the browser permits you to do so, which it isn't required to do—using CSS:

#### CSS

    tt {
      font-family: "Lucida Console", "Menlo", "Monaco", "Courier",
                   monospace;
    }

#### HTML

    <p>Enter the following at the telnet command prompt: <code>set localecho</code><br />

    The telnet client should display: <tt>Local Echo is on</tt></p>

#### Result

Usage notes
-----------

The `<tt>` element is, by default, rendered using the browser's default non-proportional font. You can override this using CSS by creating a rule using the `tt` selector, as seen in the example [Overriding the default font](#overriding_the_default_font) above.

User-configured changes to the default monospace font setting may take precedence over your CSS.

Although this element wasn't officially deprecated in HTML 4.01, its use was discouraged in favor of the semantic elements and/or CSS. The `<tt>` element is obsolete in HTML 5.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/html52/obsolete.html#elementdef-tt">HTML5<br />
<span class="small">The definition of '&lt;tt&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html401/present/graphics.html#h-15.2.1">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;tt&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`tt`

Yes

12

Yes

Before Firefox 4, this element implemented the `HTMLSpanElement` interface instead of the standard `HTMLElement` interface.

Yes

Yes

Yes

Yes

Yes

Yes

Before Firefox 4, this element implemented the `HTMLSpanElement` interface instead of the standard `HTMLElement` interface.

Yes

Yes

Yes

See also
--------

-   The semantic [`<code>`](code), [`<var>`](var), [`<kbd>`](kbd), and [`<samp>`](samp) elements
-   The [`<pre>`](pre) element for displaying preformatted text blocks

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tt" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tt</a>
