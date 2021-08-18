KeyboardEvent.shiftKey
======================

The `KeyboardEvent.shiftKey` read-only property is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates if the shift key was pressed (`true`) or not (`false`) when the event occurred.

Syntax
------

    var shiftKeyPressed = instanceOfKeyboardEvent.shiftKey

### Return value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)

Example
-------

    <html>
    <head>
    <title>shiftKey example</title>

    <script type="text/javascript">

    function showChar(e){
      alert(
        "Key Pressed: " + String.fromCharCode(e.charCode) + "\n"
        + "charCode: " + e.charCode + "\n"
        + "SHIFT key pressed: " + e.shiftKey + "\n"
        + "ALT key pressed: " + e.altKey + "\n"
      );
    }

    </script>
    </head>

    <body onkeypress="showChar(event);">
    <p>Press any character key, with or without holding down
     the SHIFT key.<br />
    You can also use the SHIFT key together with the ALT key.</p>
    </body>
    </html>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-KeyboardEvent-shiftKey">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'KeyboardEvent.shiftKey' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`shiftKey`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`KeyboardEvent`](../keyboardevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/shiftKey" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/shiftKey</a>
