# Element: mouseout event

The `mouseout` event is fired at an [`Element`](../element) when a pointing device (usually a mouse) is used to move the cursor so that it is no longer contained within the element or one of its children. `mouseout` is also delivered to an element if the cursor enters a child element, because the child element obscures the visible area of the element.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../mouseevent"><code>MouseEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onmouseout"><code>onmouseout</code></a></td></tr></tbody></table>

## Examples

The following examples show the use of the `mouseout` event.

### mouseout and mouseleave

The following example illustrates the difference between `mouseout` and [`mouseleave`](mouseleave_event) events. The `mouseleave` event is added to the [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) to color the list purple whenever the mouse exits the `<ul>`. `mouseout` is added to the list to color the targeted element orange when the mouse exits it.

When you try this out, you'll find that `mouseout` is delivered to the individual list items, while `mouseleave` goes to the overall list, courtesy of the hierarchy of the items and the fact that list items obscure the underlying `<ul>`.

#### HTML

    <ul id="test">
      <li>item 1</li>
      <li>item 2</li>
      <li>item 3</li>
    </ul>

#### JavaScript

    let test = document.getElementById("test");

    // Briefly make the list purple when the mouse moves off the
    // <ul> element
    test.addEventListener("mouseleave", function( event ) {
      // highlight the mouseleave target
      event.target.style.color = "purple";

      // reset the color after a short delay
      setTimeout(function() {
        event.target.style.color = "";
      }, 1000);
    }, false);

    // Briefly make an <li> orange when the mouse moves off of it
    test.addEventListener("mouseout", function( event ) {
      // highlight the mouseout target
      event.target.style.color = "orange";

      // reset the color after a short delay
      setTimeout(function() {
        event.target.style.color = "";
      }, 500);
    }, false);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-mouseout">UI Events<br />
<span class="small">The definition of 'mouseout' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#event-type-mouseout">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'mouseout' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

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

`mouseout_event`

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

- [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)
- [`mousedown`](mousedown_event)
- [`mouseup`](mouseup_event)
- [`mousemove`](mousemove_event)
- [`click`](click_event)
- [`dblclick`](dblclick_event)
- [`mouseover`](mouseover_event)
- [`mouseenter`](mouseenter_event)
- [`mouseleave`](mouseleave_event)
- [`contextmenu`](contextmenu_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseout_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseout_event</a>
