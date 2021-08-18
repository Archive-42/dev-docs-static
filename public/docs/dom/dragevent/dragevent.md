# DragEvent()

This constructor is used to create a synthetic [`DragEvent`](../dragevent) object.

Although this interface has a constructor, it is not possible to create a useful [`DataTransfer`](../datatransfer) object from script, since [`DataTransfer`](../datatransfer) objects have a processing and security model that is coordinated by the browser during drag-and-drops.

This interface inherits properties from [`MouseEvent`](../mouseevent) and [`Event`](../event).

## Syntax

     event = new DragEvent(type, DragEventInit);

### Arguments

_type_  
Is a `DOMString` representing the name of the event (see [DragEvent event types](../dragevent#event_types)).

_DragEventInit_<span class="badge inline optional">Optional</span>  
Is a `DragEventInit` dictionary, having the following fields:

- `"dataTransfer"`, optional and defaults to `"null"`. The type is `DataTransfer`.

The `DragEventInit` dictionary inherits from the [`MouseEventInit dictionary`](../mouseevent/mouseevent).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#the-dragevent-interface">HTML Living Standard<br />
<span class="small">The definition of 'DragEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#the-dragevent-interface">HTML 5.1<br />
<span class="small">The definition of 'DragEvent' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`DragEvent`

46

12

3.5

No

12

3.1

No

No

Yes

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DragEvent/DragEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DragEvent/DragEvent</a>
