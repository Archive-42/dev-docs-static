# Event.cancelBubble

The `cancelBubble` property of the [`Event`](../event) interface is a historical alias to [`Event.stopPropagation()`](stoppropagation). Setting its value to `true` before returning from an event handler prevents propagation of the event. In later implementations, setting this to `false` does nothing. See [Browser compatibility](#browser_compatibility) for details.

## Syntax

    event.cancelBubble = bool;
    var bool = event.cancelBubble;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

## Example

    elem.onclick = function(event) {
      // Do cool things here
      event.cancelBubble = true;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-event-cancelbubble">DOM<br />
<span class="small">The definition of 'cancelBubble' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`cancelBubble`

Yes

Starting with Chrome 58 and Opera 45, setting this property to false does nothing, as per [spec discussion](https://github.com/whatwg/dom/issues/211).

12

53

1-53

Only supported for [`UIEvent`](https://developer.mozilla.org/docs/Web/API/UIEvent), not all `Event` objects.

Yes

Yes

Starting with Chrome 58 and Opera 45, setting this property to false does nothing, as per [spec discussion](https://github.com/whatwg/dom/issues/211).

Yes

Yes

Starting with Chrome 58 and Opera 45, setting this property to false does nothing, as per [spec discussion](https://github.com/whatwg/dom/issues/211).

Yes

Starting with Chrome 58 and Opera 45, setting this property to false does nothing, as per [spec discussion](https://github.com/whatwg/dom/issues/211).

53

4-53

Only supported for [`UIEvent`](https://developer.mozilla.org/docs/Web/API/UIEvent), not all `Event` objects.

Yes

Starting with Chrome 58 and Opera 45, setting this property to false does nothing, as per [spec discussion](https://github.com/whatwg/dom/issues/211).

Yes

Yes

Starting with Samsung Internet 7.0 and Opera 45, setting this property to false does nothing, as per [spec discussion](https://github.com/whatwg/dom/issues/211).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/cancelBubble" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/cancelBubble</a>
