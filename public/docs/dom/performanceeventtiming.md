# PerformanceEventTiming

The `PerformanceEventTiming` interface of the Event Timing API provides timing information for the event types listed below.

- `auxclick`
- `beforeinput`
- `click`
- `compositionend`
- `compositionstart`
- `compositionupdate`
- `contextmenu`
- `dblclick`
- `dragend`
- `dragenter`
- `dragleave`
- `dragover`
- `dragstart`
- `drop`
- `input`
- `keydown`
- `keypress`
- `keyup`
- `mousedown`
- `mouseenter`
- `mouseleave`
- `mouseout`
- `mouseover`
- `mouseup`
- `pointerover`
- `pointerenter`
- `pointerdown`
- `pointerup`
- `pointercancel`
- `pointerout`
- `pointerleave`
- `gotpointercapture`
- `lostpointercapture`
- `touchstart`
- `touchend`
- `touchcancel`

## Properties

`PerformanceEventTiming.processingStart`  
Returns the time at which event dispatch started.

`PerformanceEventTiming.processingEnd`  
Returns the time at which the event dispatch ended.

`PerformanceEventTiming.cancelable`  
Returns the associated event's cancelable attribute.

`PerformanceEventTiming.target`  
Returns the associated event's last target, if it is not removed.

## Methods

`PerformanceEventTiming.toJSON()`  
Converts the PerformanceEventTiming object to JSON.

## Examples

The following example shows how to use the API for all events:

    const observer = new PerformanceObserver(function(list) {
        const perfEntries = list.getEntries().forEach(entry => {
            // Full duration
            const inputDuration = entry.duration;
            // Input delay (before processing event)
            const inputDelay = entry.processingStart - entry.startTime;
            // Synchronous event processing time (between start and end dispatch).
            const inputSyncProcessingTime = entry.processingEnd - entry.processingStart;
        });
    });
    // Register observer for event.
    observer.observe({entryTypes: ["event"]});

We can also directly query the [first input delay](https://web.dev/fid). The first input delay or FID, measures the time from when a user first interacts with a page (i.e. when they click a link or tap on a button) to the time when the browser is actually able to begin processing event handlers in response to that interaction.

    // Keep track of whether (and when) the page was first hidden, see:
    // https://github.com/w3c/page-visibility/issues/29
    // NOTE: ideally this check would be performed in the document <head>
    // to avoid cases where the visibility state changes before this code runs.
    let firstHiddenTime = document.visibilityState === 'hidden' ? 0 : Infinity;
    document.addEventListener('visibilitychange', (event) => {
      firstHiddenTime = Math.min(firstHiddenTime, event.timeStamp);
    }, {once: true});

    // Sends the passed data to an analytics endpoint. This code
    // uses `/analytics`; you can replace it with your own URL.
    function sendToAnalytics(data) {
      const body = JSON.stringify(data);
      // Use `navigator.sendBeacon()` if available, falling back to `fetch()`.
      (navigator.sendBeacon && navigator.sendBeacon('/analytics', body)) ||
          fetch('/analytics', {body, method: 'POST', keepalive: true});
    }

    // Use a try/catch instead of feature detecting `first-input`
    // support, since some browsers throw when using the new `type` option.
    // https://bugs.webkit.org/show_bug.cgi?id=209216
    try {
      function onFirstInputEntry(entry) {
        // Only report FID if the page wasn't hidden prior to
        // the entry being dispatched. This typically happens when a
        // page is loaded in a background tab.
        if (entry.startTime < firstHiddenTime) {
          const fid = entry.processingStart - entry.startTime;

          // Report the FID value to an analytics endpoint.
          sendToAnalytics({fid});
        }
      }

      // Create a PerformanceObserver that calls `onFirstInputEntry` for each entry.
      const po = new PerformanceObserver((entryList) => {
        entryList.getEntries().forEach(onFirstInputEntry);
      });

      // Observe entries of type `first-input`, including buffered entries,
      // i.e. entries that occurred before calling `observe()` below.
      po.observe({
        type: 'first-input',
        buffered: true,
      });
    } catch (e) {
      // Do nothing if the browser doesn't support this API.
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/event-timing/#sec-performance-event-timing">Event Timing API<br />
<span class="small">The definition of 'PerformanceEventTiming' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PerformanceEventTiming`

77

80

No

No

Yes

No

77

77

No

Yes

No

12.0

`cancelable`

77

80

No

No

Yes

No

77

77

No

Yes

No

12.0

`processingEnd`

77

80

No

No

Yes

No

77

77

No

Yes

No

12.0

`processingStart`

77

80

No

No

Yes

No

77

77

No

Yes

No

12.0

`target`

85

85

No

No

71

No

85

85

No

60

No

14.0

`toJSON`

77

80

No

No

Yes

No

77

77

No

Yes

No

12.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceEventTiming" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceEventTiming</a>
