# Event.timeStamp

The `timeStamp` read-only property of the [`Event`](../event) interface returns the time (in milliseconds) at which the event was created.

**Note:** This property only works if the event system supports it for the particular event.

## Syntax

    time = event.timeStamp;

### Value

This value is the number of milliseconds elapsed from the beginning of the current [document's lifetime](../performance/timeorigin) till the event was created.

In newer implementations, the value is a [`DOMHighResTimeStamp`](../domhighrestimestamp) accurate to 5 microseconds (0.005 ms). In older implementations, the value is a [`DOMTimeStamp`](../domtimestamp), accurate to a millisecond.

## Example

### HTML

    <p>
      Focus this iframe and press any key to get the
      current timestamp for the keypress event.
    </p>
    <p>timeStamp: <span id="time">-</span></p>

### JavaScript

    function getTime(event) {
      var time = document.getElementById("time");
      time.firstChild.nodeValue = event.timeStamp;
    }
    document.body.addEventListener("keypress", getTime);

### Result

## Reduced time precision

To offer protection against timing attacks and fingerprinting, the precision of `Event.timeStamp` might get rounded depending on browser settings.

In Firefox, the `privacy.reduceTimerPrecision` preference is enabled by default and defaults to 20us in Firefox 59; in 60 it will be 2ms.

    // reduced time precision (2ms) in Firefox 60
    event.timeStamp;
    // 1519211809934
    // 1519211810362
    // 1519211811670
    // ...

    // reduced time precision with `privacy.resistFingerprinting` enabled
    event.timeStamp;
    // 1519129853500
    // 1519129858900
    // 1519129864400
    // ...

In Firefox, if you also enable `privacy.resistFingerprinting`, the precision will be 100ms or the value of `privacy.resistFingerprinting.reduceTimerPrecision.microseconds`, whichever is larger.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-event-timestamp">DOM<br />
<span class="small">The definition of 'Event.timeStamp' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`timeStamp`

49

Starting with Chrome 49, Firefox 54 and Opera 36, this property returns [`DOMHighResTimeStamp`](https://developer.mozilla.org/docs/Web/API/DOMHighResTimeStamp) instead of [`DOMTimeStamp`](https://developer.mozilla.org/docs/Web/API/DOMTimeStamp).

12

Yes

Starting with Chrome 49, Firefox 54 and Opera 36, this property returns [`DOMHighResTimeStamp`](https://developer.mozilla.org/docs/Web/API/DOMHighResTimeStamp) instead of [`DOMTimeStamp`](https://developer.mozilla.org/docs/Web/API/DOMTimeStamp).

Yes

Starting with Chrome 49, Firefox 54 and Opera 36, this property returns [`DOMHighResTimeStamp`](https://developer.mozilla.org/docs/Web/API/DOMHighResTimeStamp) instead of [`DOMTimeStamp`](https://developer.mozilla.org/docs/Web/API/DOMTimeStamp).

36

Starting with Chrome 49, Firefox 54 and Opera 36, this property returns [`DOMHighResTimeStamp`](https://developer.mozilla.org/docs/Web/API/DOMHighResTimeStamp) instead of [`DOMTimeStamp`](https://developer.mozilla.org/docs/Web/API/DOMTimeStamp).

Yes

49

Starting with version 49, this property returns [`DOMHighResTimeStamp`](https://developer.mozilla.org/docs/Web/API/DOMHighResTimeStamp) instead of [`DOMTimeStamp`](https://developer.mozilla.org/docs/Web/API/DOMTimeStamp).

49

Starting with Chrome 49, Firefox 54 and Opera 36, this property returns [`DOMHighResTimeStamp`](https://developer.mozilla.org/docs/Web/API/DOMHighResTimeStamp) instead of [`DOMTimeStamp`](https://developer.mozilla.org/docs/Web/API/DOMTimeStamp).

Yes

Starting with Chrome 49, Firefox 54 and Opera 36, this property returns [`DOMHighResTimeStamp`](https://developer.mozilla.org/docs/Web/API/DOMHighResTimeStamp) instead of [`DOMTimeStamp`](https://developer.mozilla.org/docs/Web/API/DOMTimeStamp).

36

Starting with Chrome 49, Firefox 54 and Opera 36, this property returns [`DOMHighResTimeStamp`](https://developer.mozilla.org/docs/Web/API/DOMHighResTimeStamp) instead of [`DOMTimeStamp`](https://developer.mozilla.org/docs/Web/API/DOMTimeStamp).

Yes

5.0

Starting with Samsung Internet 5.0, Firefox 54 and Opera 36, this property returns [`DOMHighResTimeStamp`](https://developer.mozilla.org/docs/Web/API/DOMHighResTimeStamp) instead of [`DOMTimeStamp`](https://developer.mozilla.org/docs/Web/API/DOMTimeStamp).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/timeStamp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/timeStamp</a>
