# MouseEvent.screenY

The `screenY` read-only property of the [`MouseEvent`](../mouseevent) interface provides the vertical coordinate (offset) of the mouse pointer in global (screen) coordinates.

## Syntax

    var y = instanceOfMouseEvent.screenY

### Return value

A `double` floating point value. Early versions of the spec defined this as an integer referring to the number of pixels. See the "Browser compatibility" section for details.

## Example

This example displays your mouse's coordinates whenever you trigger the `mousemove` event.

### HTML

    <p>Move your mouse to see its position.</p>
    <p id="screen-log"></p>

### JavaScript

    let screenLog = document.querySelector('#screen-log');
    document.addEventListener('mousemove', logKey);

    function logKey(e) {
      screenLog.innerText = `
        Screen X/Y: ${e.screenX}, ${e.screenY}
        Client X/Y: ${e.clientX}, ${e.clientY}`;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-mouseevent-screeny">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'screenY' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Redefines <a href="../mouseevent"><code>MouseEvent</code></a> from long to double.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-MouseEvent-screenY">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'MouseEvent.screenY' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html">Document Object Model (DOM) Level 2 Events Specification</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-MouseEvent">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'MouseEvent.sceenY' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`screenY`

Yes

12

Yes

9

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`long_to_double`

56

≤79

?

?

?

?

56

56

?

?

?

6.0

## See also

- [`MouseEvent`](../mouseevent)
- [`screenX`](screenx)
- [`clientX`](clientx) / [`clientY`](clienty)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/screenY" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/screenY</a>
