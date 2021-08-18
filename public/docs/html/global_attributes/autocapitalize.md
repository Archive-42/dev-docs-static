autocapitalize
==============

The `autocapitalize` [global attribute](../global_attributes) is an enumerated attribute that controls whether and how text input is automatically capitalized as it is entered/edited by the user. The attribute must take one of the following values:

-   `off` or `none`: No autocapitalization is applied (all letters default to lowercase)
-   `on` or `sentences`: The first letter of each sentence defaults to a capital letter; all other letters default to lowercase
-   `words`: The first letter of each word defaults to a capital letter; all other letters default to lowercase
-   `characters`: All letters should default to uppercase

The `autocapitalize` attribute doesn’t affect behavior when typing on a physical keyboard. Instead, it affects the behavior of other input mechanisms, such as virtual keyboards on mobile devices and voice input. The behavior of such mechanisms is that they often assist users by automatically capitalizing the first letter of sentences. The `autocapitalize` attribute enables authors to override that behavior per-element.

The `autocapitalize` attribute never causes autocapitalization to be enabled for an [`<input>`](../element/input) element with a [`type`](../element/input#attr-type) attribute whose value is `url`, `email`, or `password`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#attr-autocapitalize">HTML Living Standard<br />
<span class="small">The definition of 'autocapitalize' in that specification.</span></a></td></tr></tbody></table>

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

`autocapitalize`

43

79

83

?

?

No

43

43

83

?

5

?

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/autocapitalize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/autocapitalize</a>
