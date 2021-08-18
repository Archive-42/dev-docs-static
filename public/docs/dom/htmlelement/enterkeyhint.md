HTMLElement.enterKeyHint
========================

The `enterKeyHint` property is an enumerated property defining what action label (or icon) to present for the enter key on virtual keyboards.  
It reflects the [`enterkeyhint`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/enterkeyhint) HTML global attribute and is an enumerated property, only accepting the following values as a [`DOMString`](../domstring):

-   `'enter'` typically indicating inserting a new line.
-   `'done'` typically meaning there is nothing more to input and the input method editor (IME) will be closed.
-   `'go'` typically meaning to take the user to the target of the text they typed.
-   `'next'` typically taking the user to the next field that will accept text.
-   `'previous'` typically taking the user to the previous field that will accept text.
-   `'search'` typically taking the user to the results of searching for the text they have typed.
-   `'send'` typically delivering the text to its target.

If no `enterKeyHint` value has been specified or if it was set to a different value than the allowed ones, it will return an empty string.

Examples
--------

Give a virtual keyboard a hint how to label the enter key (might render as Send and Search, depending on the OS or the user's language).

    const send = document.getElementById('sendInput');
    const search = document.getElementById('searchInput');

    send.enterKeyHint = 'send';
    search.enterKeyHint = 'search';

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dom-enterkeyhint">HTML Living Standard<br />
<span class="small">The definition of 'enterKeyHint' in that specification.</span></a></td></tr></tbody></table>

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

`enterKeyHint`

77

79

79

No

64

13.1

77

77

79

55

13.4

12.0

See also
--------

-   [`enterkeyhint`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/enterkeyhint) HTML global attribute

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/enterKeyHint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/enterKeyHint</a>
