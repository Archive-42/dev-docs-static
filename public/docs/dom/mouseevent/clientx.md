# MouseEvent.clientX

The `clientX` read-only property of the [`MouseEvent`](../mouseevent) interface provides the horizontal coordinate within the application's [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport) at which the event occurred (as opposed to the coordinate within the page).

For example, clicking on the left edge of the viewport will always result in a mouse event with a `clientX` value of `0`, regardless of whether the page is scrolled horizontally.

## Syntax

    var x = instanceOfMouseEvent.clientX

### Return value

A `double` floating point value, as redefined by the CSSOM View Module. Originally, this property was defined as a `long` integer. See the "Browser compatibility" section for details.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-mouseevent-clientx">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'clientX' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Redefines <a href="../mouseevent"><code>MouseEvent</code></a> from <code>long</code> to <code>double</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-MouseEvent-clientX">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'MouseEvent.clientX' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html">Document Object Model (DOM) Level 2 Events Specification</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-MouseEvent">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'MouseEvent.clientX' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`clientX`

1

12

1

9

10.6

3.1

1

18

4

11

2

1.0

`long_to_double`

56

???79

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
- [`clientY`](clienty)
- [`screenX`](screenx) / [`screenY`](screeny)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/clientX" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/clientX</a>
