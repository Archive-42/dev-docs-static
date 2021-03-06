Window.alert()
==============

`window.alert()` instructs the browser to display a dialog with an optional message, and to wait until the user dismisses the dialog.

Under some conditions — for example, when the user switches tabs — the browser may not actually display a dialog, or may not wait for the user to dismiss the dialog.

Syntax
------

    window.alert(message);

### Parameters

 `message` <span class="badge inline optional">Optional</span>   
A string you want to display in the alert dialog, or, alternatively, an object that is converted into a string and displayed.

Example
-------

    window.alert("Hello world!");
    alert("Hello world!");

Both produce:

<img src="data:image/png;base64,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" width="326" height="125" />

Notes
-----

The alert dialog should be used for messages which do not require any response on the part of the user, other than the acknowledgement of the message.

<span class="comment">The following text is shared between this article, DOM:window.prompt and DOM:window.confirm</span> Dialog boxes are modal windows - they prevent the user from accessing the rest of the program's interface until the dialog box is closed. For this reason, you should not overuse any function that creates a dialog box (or modal window).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/timers-and-user-prompts.html#dom-alert">HTML Living Standard<br />
<span class="small">The definition of 'alert()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`alert`

1

Starting with Chrome 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

12

1

4

3

Starting with Opera 33, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

1

1

Starting with WebView 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

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

-   [`confirm`](confirm)
-   [`prompt`](prompt)
-   For [Mozilla Chrome](https://developer.mozilla.org/en-US/docs/Glossary/Chrome) see `nsIPromptService.alert()` and `nsIPromptService.alertCheck()`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/alert" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/alert</a>
