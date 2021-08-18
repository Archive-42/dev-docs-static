spellcheck
==========

The `spellcheck` [global attribute](../global_attributes) is an enumerated attribute defines whether the element may be checked for spelling errors.

It may have the following values:

-   `true`, which indicates that the element should be, if possible, checked for spelling errors;
-   `false`, which indicates that the element should not be checked for spelling errors.

**Note:** The `spellcheck` attribute is an *enumerated* one and not a *Boolean* one. This means that the explicit usage of one of the values `true` or `false` is mandatory, and that a shorthand like `<textarea spellcheck></textarea>` is not allowed. The correct usage is `<textarea spellcheck="true"></textarea>`.

If this attribute is not set, its default value is element-type and browser-defined. This default value may also be *inherited*, which means that the element content will be checked for spelling errors only if its nearest ancestor has a *spellcheck* state of `true`.

This attribute is merely a hint for the browser: browsers are not required to check for spelling errors. Typically non-editable elements are not checked for spelling errors, even if the `spellcheck` attribute is set to `true` and the browser supports spellchecking.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#attr-spellcheck">HTML Living Standard<br />
<span class="small">The definition of 'spellcheck' in that specification.</span></a></td></tr></tbody></table>

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

`spellcheck`

9

12

Yes

11

Yes

Yes

47

47

57

37

9.3

5.0

See also
--------

-   All [global attributes](../global_attributes).

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/spellcheck" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/spellcheck</a>
