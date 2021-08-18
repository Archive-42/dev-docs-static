inputmode
=========

The `inputmode` [global attribute](../global_attributes) is an enumerated attribute that hints at the type of data that might be entered by the user while editing the element or its contents. It can have the following values:

`none`  
No virtual keyboard. For when the page implements its own keyboard input control.

 `text` (default value)  
Standard input keyboard for the user's current locale.

`decimal`  
Fractional numeric input keyboard containing the digits and decimal separator for the user's locale (typically . or ,). Devices may or may not show a minus key (-).

`numeric`  
Numeric input keyboard, but only requires the digits 0–9. Devices may or may not show a minus key.

`tel`  
A telephone keypad input, including the digits 0–9, the asterisk (\*), and the pound (\#) key. Inputs that *require* a telephone number should typically use `<input type="tel">`instead.

`search`  
A virtual keyboard optimized for search input. For instance, the [return/submit key](https://html.spec.whatwg.org/dev/interaction.html#input-modalities:-the-enterkeyhint-attribute) may be labeled “Search”, along with possible other optimizations. Inputs that *require* a search query should typically use `<input type="search">` instead.

`email`  
A virtual keyboard optimized for entering email addresses. Typically includes the @ character as well as other optimizations. Inputs that *require* email addresses should typically use `<input type="email">` instead.

`url`  
A keypad optimized for entering URLs. This may have the / key more prominent, for example. Enhanced features could include history access and so on. Inputs that *require* a URL should typically use `<input type="url">` instead.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#attr-inputmode">HTML Living Standard<br />
<span class="small">The definition of 'inputmode' in that specification.</span></a></td></tr></tbody></table>

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

`inputmode`

66

79

23

\["Before version 77, Firefox does not support `inputmode` when `contenteditable` is `true`.", "Before version 75, Firefox accepts values from an earlier specification. From version 75, it accepts values from the WHATWG Living Standard. See [bug 1509527](https://bugzil.la/1509527)."\]

17-23

No

53

No

66

66

79

68

47

12.2

9.0

See also
--------

-   All [global attributes](../global_attributes).
-   [`enterkeyhint`](enterkeyhint) global attribute

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/inputmode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/inputmode</a>
