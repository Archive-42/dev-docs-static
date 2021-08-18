# Element: dblclick event

The `dblclick` event fires when a pointing device button (such as a mouse's primary button) is double-clicked; that is, when it's rapidly clicked twice on a single element within a very short span of time.

`dblclick` fires after two [`click`](click_event) events (and by extension, after two pairs of [`mousedown`](mousedown_event) and [`mouseup`](mouseup_event) events).

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../mouseevent"><code>MouseEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/ondblclick"><code>ondblclick</code></a></td></tr></tbody></table>

## Examples

This example toggles the size of a card when you double click on it.

### JavaScript

    const card = document.querySelector('aside');

    card.addEventListener('dblclick', function (e) {
      card.classList.toggle('large');
    });

### HTML

    <aside>
      <h3>My Card</h3>
      <p>Double click to resize this object.</p>
    </aside>

### CSS

    aside {
      background: #fe9;
      border-radius: 1em;
      display: inline-block;
      padding: 1em;
      transform: scale(.9);
      transform-origin: 0 0;
      transition: transform .6s;
      user-select: none;
    }

    .large {
      transform: scale(1.3);
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-dblclick">UI Events<br />
<span class="small">The definition of 'dblclick' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#event-type-dblclick">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'dblclick' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

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

`dblclick_event`

1

12

6

Starting in Firefox 68, `dblclick` events are only sent for the primary mouse button, per the specification.

11

11.6

3

No

No

6

12.1

1

No

## See also

- [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)
- [`auxclick`](auxclick_event)
- [`click`](click_event)
- [`contextmenu`](contextmenu_event)
- [`mousedown`](mousedown_event)
- [`mouseup`](mouseup_event)
- [`pointerdown`](../htmlelement/pointerdown_event)
- [`pointerup`](../htmlelement/pointerup_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/dblclick_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/dblclick_event</a>
