Window.toolbar
==============

The `Window.toolbar` property returns the toolbar object, which can be used to check the browser toolbar visibility.

Syntax
------

    objRef = window.toolbar

Example
-------

The following complete HTML example demonstrates how the `visible` property of the `toolbar` object is used.

    <html>
    <head>
      <title>Various DOM Tests</title>
      <script>
        var visible = window.toolbar.visible;
      </script>
    </head>
    <body>
      <p>Various DOM Tests</p>
    </body>
    </html>

Very old versions of Firefox also allowed the toolbar visibility to be *set*, but the mechanisms that supported this [have been removed](https://developer.mozilla.org/en-US/docs/Archive/Misc_top_level/Bypassing_Security_Restrictions_and_Signing_Code).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/browsers.html#dom-window-toolbar">HTML Living Standard<br />
<span class="small">The definition of 'Window.toolbar' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#dom-window-toolbar">HTML5<br />
<span class="small">The definition of 'Window.toolbar' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`toolbar`

1

12

1

No

15

3

1

18

4

14

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/toolbar" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/toolbar</a>
