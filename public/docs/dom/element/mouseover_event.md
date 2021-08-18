# Element: mouseover event

The `mouseover` event is fired at an [`Element`](../element) when a pointing device (such as a mouse or trackpad) is used to move the cursor onto the element or one of its child elements.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../mouseevent"><code>MouseEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onmouseover"><code>onmouseover</code></a></td></tr></tbody></table>

## Examples

The following example illustrates the difference between `mouseover` and [`mouseenter`](mouseenter_event) events.

### HTML

    <ul id="test">
      <li>item 1</li>
      <li>item 2</li>
      <li>item 3</li>
    </ul>

### JavaScript

    let test = document.getElementById("test");

    // This handler will be executed only once when the cursor
    // moves over the unordered list
    test.addEventListener("mouseenter", function( event ) {
      // highlight the mouseenter target
      event.target.style.color = "purple";

      // reset the color after a short delay
      setTimeout(function() {
        event.target.style.color = "";
      }, 500);
    }, false);

    // This handler will be executed every time the cursor
    // is moved over a different list item
    test.addEventListener("mouseover", function( event ) {
      // highlight the mouseover target
      event.target.style.color = "orange";

      // reset the color after a short delay
      setTimeout(function() {
        event.target.style.color = "";
      }, 500);
    }, false);

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-mouseover">UI Events<br />
<span class="small">The definition of 'mouseover' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#event-type-mouseover">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'mouseover' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

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

`mouseover_event`

2

12

6

9

9.5

4

≤37

18

6

10.1

3.2

1.0

## See also

- [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)
- [`mousedown`](mousedown_event)
- [`mouseup`](mouseup_event)
- [`mousemove`](mousemove_event)
- [`click`](click_event)
- [`dblclick`](dblclick_event)
- [`mouseover`](mouseover_event)
- [`mouseout`](mouseout_event)
- [`mouseenter`](mouseenter_event)
- [`mouseleave`](mouseleave_event)
- [`contextmenu`](contextmenu_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseover_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseover_event</a>
