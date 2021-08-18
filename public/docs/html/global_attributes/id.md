id
==

The **`id` [global attribute](../global_attributes)** defines an identifier (ID) which must be unique in the whole document. Its purpose is to identify the element when linking (using a [fragment identifier](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Identifying_resources_on_the_Web#fragment)), scripting, or styling (with [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS)).

This attribute's value is an opaque string: this means that web authors should not rely on it to convey human-readable information (although having your IDs somewhat human-readable can be useful for code comprehension, e.g. consider `ticket-18659` versus `r45tgfe-freds&$@`).

`id`'s value must not contain [whitespace](https://developer.mozilla.org/en-US/docs/Glossary/Whitespace) (spaces, tabs etc.). Browsers treat non-conforming IDs that contain whitespace as if the whitespace is part of the ID. In contrast to the [`class`](../global_attributes#attr-class) attribute, which allows space-separated values, elements can only have one single ID value.

**Note:** Using characters except [ASCII](https://developer.mozilla.org/en-US/docs/Glossary/ASCII) letters, digits, `'_'`, `'-'` and `'.'` may cause compatibility problems, as they weren't allowed in HTML 4. Though this restriction has been lifted in [HTML5](https://developer.mozilla.org/en-US/docs/Glossary/HTML5), an ID should start with a letter for compatibility.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/dom.html#the-id-attribute">HTML Living Standard<br />
<span class="small">The definition of 'id' in that specification.</span></a></td></tr></tbody></table>

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

`id`

Yes

12

32

Yes-32

`id` is a true global attribute only since Firefox 32.

Yes

Yes

Yes

Yes

Yes

32

Yes-32

`id` is a true global attribute only since Firefox 32.

Yes

Yes

Yes

See also
--------

-   All [global attributes](../global_attributes).
-   [`Element.id`](https://developer.mozilla.org/en-US/docs/Web/API/Element/id) that reflects this attribute.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/id" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/id</a>
