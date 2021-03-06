Window.confirm()
================

`window.confirm()` instructs the browser to display a dialog with an optional message, and to wait until the user either confirms or cancels the dialog.

Under some conditions — for example, when the user switches tabs — the browser may not actually display a dialog, or may not wait for the user to confirm or cancel the dialog.

Syntax
------

    result = window.confirm(message);

### Parameters

`message`  
A string you want to display in the confirmation dialog.

### Return value

A boolean indicating whether OK (`true`) or Cancel (`false`) was selected. If a browser is ignoring in-page dialogs, then the returned value is always `false`.

Example
-------

    if (window.confirm("Do you really want to leave?")) {
      window.open("exit.html", "Thanks for Visiting!");
    }

Produces:

<img src="data:image/png;base64,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" alt="firefox confirm" width="354" height="119" />  

Notes
-----

<span class="comment">The following text is shared between this article, DOM:window.prompt and DOM:window.alert</span> Dialog boxes are modal windows — they prevent the user from accessing the rest of the program's interface until the dialog box is closed. For this reason, you should not overuse any function that creates a dialog box (or modal window). Regardless, there are good reasons to [avoid using dialog boxes for confirmation](https://alistapart.com/article/neveruseawarning/).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/timers-and-user-prompts.html#dom-confirm">HTML Living Standard<br />
<span class="small">The definition of 'confirm()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`confirm`

1

Starting with Chrome 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

12

1

4

3

Starting with Opera 33, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

1

1

Starting with Chrome 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

18

Starting with Chrome 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

4

10.1

Starting with Opera 33, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

1

1.0

Starting with Samsung Internet 5.0, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

See also
--------

-   [`window.alert()`](alert)
-   [`window.prompt()`](prompt)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/confirm" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/confirm</a>
