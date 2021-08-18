&lt;big&gt;: The Bigger Text element
====================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The obsolete **HTML Big Element** (`<big>`) renders the enclosed text at a font size one level larger than the surrounding text (`medium` becomes `large`, for example). The size is capped at the browser's maximum permitted font size.

**Usage note:** As it was purely presentational, this element has been removed in [HTML5](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5) and shouldn't be used anymore. Instead web developers should use the CSS [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size) property to adjust the font size.

Attributes
----------

This element has no other attributes than the [global attributes](../global_attributes), common to all elements.

Examples
--------

Here we see examples showing the use of `<big>` followed by an example showing how to accomplish the same results using modern CSS syntax instead.

### Using `<big>`

This example uses the obsolete `<big>` element to increase the size of some text.

#### HTML

    <p>
      This is the first sentence. <big>This whole
      sentence is in bigger letters.</big>
    </p>

#### Result

### Using CSS `font-size`

This example uses the CSS [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size) property to increase the font size by one level.

#### CSS

    .bigger {
      font-size: larger;
    }

#### HTML

    <p>
      This is the first sentence. <span class="bigger">This whole
      sentence is in bigger letters.</span>
    </p>

#### Result

DOM interface
-------------

This element implements the [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) interface.

**Implementation note:** Up to Gecko 1.9.2 inclusive, Firefox implements the [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement) interface for this element.

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

`big`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   CSS: [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size), [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font)
-   HTML: [`<small>`](small), [`<font>`](font), [`<style>`](style)
-   HTML 4.01 Specification: [Font Styles](https://www.w3.org/TR/html4/present/graphics.html#h-15.2)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/big" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/big</a>
