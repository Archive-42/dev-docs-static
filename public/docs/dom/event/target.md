# Event.target

The `target` property of the [`Event`](../event) interface is a reference to the object onto which the event was dispatched. It is different from [`Event.currentTarget`](currenttarget) when the event handler is called during the bubbling or capturing phase of the event.

## Syntax

    const theTarget = someEvent.target;

### Value

[`EventTarget`](../eventtarget)

## Example

The `event.target` property can be used in order to implement **event delegation**.

    // Make a list
    const ul = document.createElement('ul');
    document.body.appendChild(ul);

    const li1 = document.createElement('li');
    const li2 = document.createElement('li');
    ul.appendChild(li1);
    ul.appendChild(li2);

    function hide(evt) {
      // e.target refers to the clicked <li> element
      // This is different than e.currentTarget, which would refer to the parent <ul> in this context
      evt.target.style.visibility = 'hidden';
    }

    // Attach the listener to the list
    // It will fire when each <li> is clicked
    ul.addEventListener('click', hide, false);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-event-target">DOM<br />
<span class="small">The definition of 'Event.target' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/dom/#dom-event-target">DOM4<br />
<span class="small">The definition of 'Event.target' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-Event-target">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'Event.target' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`target`

1

12

1

9

7

1

1

18

4

10.1

1

1.0

### Compatibility notes

On IE 6–8, the event model is different. Event listeners are attached with the non-standard [`EventTarget.attachEvent()`](../eventtarget/addeventlistener) method.

In this model, the event object has a [`Event.srcElement`](srcelement) property (instead of the `target` property) and it has the same semantics as `Event.target`.

    function hide(evt) {
      // Support IE6-8
      var target = evt.target || evt.srcElement;
      target.style.visibility = 'hidden';
    }

## See also

- [Comparison of Event Targets](comparison_of_event_targets)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/target" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/target</a>
