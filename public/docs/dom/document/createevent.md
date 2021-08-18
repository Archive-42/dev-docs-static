# Document.createEvent()

**Warning**

Many methods used with `createEvent`, such as `initCustomEvent`, are deprecated. Use [event constructors](../customevent) instead.

Creates an [event](../event) of the type specified. The returned object should be first initialized and can then be passed to [`EventTarget.dispatchEvent`](../eventtarget/dispatchevent).

## Syntax

    var event = document.createEvent(type);

- `event` is the created [Event](../event) object.
- `type` is a string that represents the type of event to be created. Possible event types include `"UIEvents"`, `"MouseEvents"`, `"MutationEvents"`, and `"HTMLEvents"`. See [Notes](#notes) section for details.

## Example

    // Create the event.
    var event = document.createEvent('Event');

    // Define that the event name is 'build'.
    event.initEvent('build', true, true);

    // Listen for the event.
    elem.addEventListener('build', function (e) {
      // e.target matches elem
    }, false);

    // Target can be any Element or other EventTarget.
    elem.dispatchEvent(event);

## Notes

Event type strings suitable for passing to `createEvent()` are listed in the [DOM standard — see the table in step 2](https://dom.spec.whatwg.org/#dom-document-createevent). Bear in mind that most event objects now have constructors, which are the modern recommended way to create event object instances.

Gecko supports some non-standard event object aliases, which are listed below.

<table><thead><tr class="header"><th>Event Module</th><th>Standard event object</th><th>Gecko also supports</th></tr></thead><tbody><tr class="odd"><td>Text event module</td><td><code>TextEvent</code></td><td><code>TextEvents</code></td></tr><tr class="even"><td>Keyboard event module</td><td><code>KeyboardEvent</code></td><td><code>KeyEvents</code></td></tr><tr class="odd"><td>Basic events module</td><td><code>Event</code></td><td><code>Events</code></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-createevent">DOM<br />
<span class="small">The definition of 'document.createEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`createEvent`

1

12

1

From version 67, creating touch events using this method is no longer supported.

9

7

1

1

18

4

10.1

1

1.0

## See also

- [Creating and triggering events](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/createEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/createEvent</a>
