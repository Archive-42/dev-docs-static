Window.print()
==============

Opens the Print Dialog to print the current document.

In most browsers, this method will block while the print dialog is open. However in more recent versions of Safari, it may return immediately.

Syntax
------

    window.print()

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/timers-and-user-prompts.html#printing">HTML Living Standard<br />
<span class="small">The definition of 'print()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`print`

1

Starting with Chrome 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

12

1

5

6

Starting with Opera 33, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

1.1

1

Starting with WebView 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

18

Starting with Chrome 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

No

See [bug 1247609](https://bugzil.la/1247609).

10.1

Starting with Opera 33, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

1

1.0

Starting with Samsung Internet 5.0, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

See also
--------

-   [Printing](https://developer.mozilla.org/en-US/docs/Web/Guide/Printing)
-   [`window.onbeforeprint`](../windoweventhandlers/onbeforeprint)
-   [`window.onafterprint`](../windoweventhandlers/onafterprint)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/print" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/print</a>
