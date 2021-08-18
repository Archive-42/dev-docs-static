dir
===

The `dir` [global attribute](../global_attributes) is an enumerated attribute that indicates the directionality of the element's text.

It can have the following values:

-   `ltr`, which means *left to right* and is to be used for languages that are written from the left to the right (like English);
-   `rtl`, which means *right to left* and is to be used for languages that are written from the right to the left (like Arabic);
-   `auto`, which lets the user agent decide. It uses a basic algorithm as it parses the characters inside the element until it finds a character with a strong directionality, then applies that directionality to the whole element.

**Usage notes:** This attribute is mandatory for the [`<bdo>`](../element/bdo) element where it has a different semantic meaning.

-   This attribute is *not* inherited by the [`<bdi>`](../element/bdi) element. If not set, its value is `auto`.

-   This attribute can be overridden by the CSS properties [`direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/direction) and [`unicode-bidi`](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi), if a CSS page is active and the element supports these properties.

-   As the directionality of the text is semantically related to its content and not to its presentation, it is recommended that web developers use this attribute instead of the related CSS properties when possible. That way, the text will display correctly even on a browser that doesn't support CSS or has the CSS deactivated.

-   The `auto` value should be used for data with an unknown directionality, like data coming from user input, eventually stored in a database.

Browsers might allow users to change the directionality of [`<input>`](../element/input) and [`<textarea>`](../element/textarea)s in order to assist with authoring content. Chrome and Safari provide a directionality option in the contextual menu of input fields while Internet Explorer and Edge use the key combinations Ctrl + Left Shift and Ctrl + Right Shift. Firefox uses Ctrl/Cmd + Shift + X but does NOT update the `dir` attribute value.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/dom.html#the-dir-attribute">HTML Living Standard<br />
<span class="small">The definition of 'dir' in that specification.</span></a></td></tr></tbody></table>

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

`dir`

Yes

79

Yes

No

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

-   All [global attributes](../global_attributes).
-   [`HTMLElement.dir`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/dir) that reflects this attribute.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir</a>
