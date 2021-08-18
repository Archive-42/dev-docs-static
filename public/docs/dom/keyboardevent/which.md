KeyboardEvent.which
===================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `which` read-only property of the [`KeyboardEvent`](../keyboardevent) interface returns the numeric `keyCode` of the key pressed, or the character code (`charCode`) for an alphanumeric key pressed.

Syntax
------

    var keyResult = event.which;

### Return value

-   `keyResult` contains the numeric code for a particular key pressed, depending on whether an alphanumeric or non-alphanumeric key was pressed. Please see [`KeyboardEvent.charCode`](charcode) and [`KeyboardEvent.keyCode`](keycode) for more details.

Example
-------

    <html>
    <head>
    <title>charCode/keyCode/which example</title>

    <script type="text/javascript">

    function showKeyPress(evt) {
    alert("onkeypress handler: \n"
          + "keyCode property: " + evt.keyCode + "\n"
          + "which property: " + evt.which + "\n"
          + "charCode property: " + evt.charCode + "\n"
          + "Character Key Pressed: "
          + String.fromCharCode(evt.charCode) + "\n"
         );
    }

    function keyDown(evt) {
    alert("onkeydown handler: \n"
          + "keyCode property: " + evt.keyCode + "\n"
          + "which property: " + evt.which + "\n"
         );
    }

    </script>
    </head>

    <body
     onkeypress="showKeyPress(event);"
     onkeydown="keyDown(event);"
    >

    <p>Please press any key.</p>

    </body>
    </html>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#legacy-interface-KeyboardEvent">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'KeyboardEvent.which' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition; specified as deprecated</td></tr></tbody></table>

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

`which`

4

12

2

Firefox also implements this property on the `UIEvent` interface.

9

12.1

5.1

≤37

Yes

Yes

Firefox also implements this property on the `UIEvent` interface.

12.1

5.1

Yes

See also
--------

-   [`KeyboardEvent`](../keyboardevent), the interface this property belongs too.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/which" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/which</a>
