enterkeyhint
============

The `enterkeyhint` [global attribute](../global_attributes) is an enumerated attribute defining what action label (or icon) to present for the enter key on virtual keyboards.

Description
-----------

[Form controls](https://developer.mozilla.org/en-US/docs/Learn/Forms) (such as [`<textarea>`](../element/textarea) or [`<input>`](../element/input) elements) or elements using [`contenteditable`](contenteditable) can specify an [`inputmode`](inputmode) attribute to control what kind of virtual keyboard will be used. To further improve the user's experience, the enter key can be customized specifically by providing an `enterkeyhint` attribute indicating how the enter key should be labeled (or which icon should be shown). The enter key usually represents what the user should do next; typical actions are: sending text, inserting a new line, or searching.

If no `enterkeyhint` attribute is provided, the user agent might use contextual information from the [`inputmode`](inputmode), [`type`](../element/input#input_types), or [`pattern`](../element/input#htmlattrdefpattern) attributes to display a suitable enter key label (or icon).

### Values

The `enterkeyhint` attribute is an enumerated attribute and only accepts the following values:

<table><colgroup><col style="width: 30%" /><col style="width: 50%" /><col style="width: 20%" /></colgroup><thead><tr class="header"><th>Value</th><th>Description</th><th>Example label<br />
<span class="small">(depends on user agent and user language)</span></th></tr></thead><tbody><tr class="odd"><td><code>enterkeyhint="enter"</code></td><td>Typically inserting a new line.</td><td>↵</td></tr><tr class="even"><td><code>enterkeyhint="done"</code></td><td>Typically meaning there is nothing more to input and the input method editor (IME) will be closed.</td><td>Done</td></tr><tr class="odd"><td><code>enterkeyhint="go"</code></td><td>Typically meaning to take the user to the target of the text they typed.</td><td>Open</td></tr><tr class="even"><td><code>enterkeyhint="next"</code></td><td>Typically taking the user to the next field that will accept text.</td><td>Next</td></tr><tr class="odd"><td><code>enterkeyhint="previous"</code></td><td>Typically taking the user to the previous field that will accept text.</td><td>Previous</td></tr><tr class="even"><td><code>enterkeyhint="search"</code></td><td>Typically taking the user to the results of searching for the text they have typed.</td><td>Search</td></tr><tr class="odd"><td><code>enterkeyhint="send"</code></td><td>Typically delivering the text to its target.</td><td>Send</td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#attr-enterkeyhint">HTML Living Standard<br />
<span class="small">The definition of 'enterkeyhint' in that specification.</span></a></td></tr></tbody></table>

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

`enterkeyhint`

77

79

79

No

66

13.1

77

77

79

57

13.4

12.0

See also
--------

-   [`HTMLElement.enterkeyhint`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/enterKeyHint) property reflecting this attribute
-   [`inputmode`](inputmode) global attribute
-   [`contenteditable`](contenteditable) global attribute
-   [`type`](../element/input#input_types) and [`pattern`](../element/input#htmlattrdefpattern) attributes on [`<input>`](../element/input) elements

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/enterkeyhint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/enterkeyhint</a>
