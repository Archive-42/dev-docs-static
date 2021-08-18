KeyboardEvent.altKey
====================

The `KeyboardEvent.altKey` read-only property is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates if the alt key (Option or ⌥ on OS X) was pressed (`true`) or not (`false`) when the event occurred.

Syntax
------

    var altKeyPressed = instanceOfKeyboardEvent.altKey

### Return value

[`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)

Examples
--------

    <html>
    <head>
    <title>altKey example</title>

    <script type="text/javascript">

    function showChar(e){
      alert(
        "Key KeyDown: " + String.fromCharCode(e.charCode) + "\n"
        + "charCode: " + e.charCode + "\n"
        + "ALT key KeyDown: " + e.altKey + "\n"
      );
    }

    </script>
    </head>

    <body onkeydown="showChar(event);">
    <p>
    Press any character key,
    with or without holding down the ALT key.<br />
    You can also use the SHIFT key together with the ALT key.
    </p>
    </body>
    </html>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-KeyboardEvent-altKey">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'KeyboardEvent.altkey' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`altKey`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/altKey" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/altKey</a>
