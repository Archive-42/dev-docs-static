# KeyboardEvent.ctrlKey

The `KeyboardEvent.ctrlKey` read-only property returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates if the control key was pressed (`true`) or not (`false`) when the event occurred.

## Syntax

    var ctrlKeyPressed = instanceOfKeyboardEvent.ctrlKey

### Return value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)

## Example

    <html>
    <head>
    <title>ctrlKey example</title>

    <script type="text/javascript">

    function showChar(e){
      alert(
        "Key Pressed: " + e.key + "\n"
        + "CTRL key pressed: " + e.ctrlKey + "\n"
      );
    }

    </script>
    </head>

    <body onkeypress="showChar(event);">
    <p>Press any character key, with or without holding down the CTRL key.<br />
    You can also use the SHIFT key together with the CTRL key.</p>
    </body>
    </html>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-KeyboardEvent-ctrlKey">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'KeyboardEvent.ctrlKey' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`ctrlKey`

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

## See also

- [`KeyboardEvent`](../keyboardevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/ctrlKey" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/ctrlKey</a>
