Window.getSelection()
=====================

The `Window.getSelection()` method returns a [`Selection`](../selection) object representing the range of text selected by the user or the current position of the caret.

Syntax
------

    selection = window.getSelection();

### Return value

A [`Selection`](../selection) object.

When cast to string, either by appending an empty string (`""`) or using [`Selection.toString()`](../selection/tostring), this object returns the text selected.

When called on an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) that is not displayed (eg. where `display: none` is set) Firefox will return `null`, whereas other browsers will return a [`Selection`](../selection) object with [`Selection.type`](../selection/type) set to `None`.

Examples
--------

    function foo() {
        var selObj = window.getSelection();
        alert(selObj);
        var selRange = selObj.getRangeAt(0);
        // do stuff with the range
    }

Notes
-----

### String representation of the Selection object

In JavaScript, when an object is passed to a function expecting a string (like [`window.alert()`](alert) or [`document.write()`](../document/write)), the object's [`toString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/toString) method is called and the returned value is passed to the function. This can make the object appear to be a string when used with other functions when it is really an object with properties and methods.

In the above example, `selObj.toString()` is automatically called when it is passed to [`window.alert()`](alert). However, attempting to use a JavaScript [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) property or method such as `length` or `substr` directly on a [`Selection`](../selection) object will result in an error if it does not have that property or method and may return unexpected results if it does. To use a `Selection` object as a string, call its `toString()` method directly:

    var selectedText = selObj.toString();

-   `selObj` is a `Selection` object.
-   `selectedText` is a string (Selected text).

### Related objects

You can call [`Document.getSelection()`](../document/getselection), which works identically to `Window.getSelection()`.

It is worth noting that currently `getSelection()` doesn't work on the content of [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) and [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) elements in Firefox, Edge (Legacy) and Internet Explorer. [`HTMLInputElement.setSelectionRange()`](../htmlinputelement/setselectionrange) or the `selectionStart` and `selectionEnd` properties could be used to work around this.

Notice also the difference between *selection* and *focus*. [`Document.activeElement`](../document/activeelement) returns the focused element.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#extensions-to-window-interface">Selection API<br />
<span class="small">The definition of 'Window.getSelection()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>New spec.</td></tr></tbody></table>

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

`getSelection`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

See also
--------

-   [Selection API](../selection)
-   [`Selection`](../selection)
-   [`Range`](../range)
-   [`Document.getSelection()`](../document/getselection)
-   [`HTMLInputElement.setSelectionRange()`](../htmlinputelement/setselectionrange)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/getSelection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/getSelection</a>
