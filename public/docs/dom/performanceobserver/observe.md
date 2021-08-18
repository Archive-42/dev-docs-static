# PerformanceObserver.observe()

The `observe()` method of the **[`PerformanceObserver`](../performanceobserver)** interface is used to specify the set of performance entry types to observe. The performance entry types are specified as an array of [`DOMString`](../domstring) objects, each naming one entry type; the type names are documented in [Performance entry type names](#) in [PerformanceEntry.entryType](../performanceentry/entrytype).

When a matching performance entry is recorded, the performance observer's callback function—set when creating the [`PerformanceObserver`](../performanceobserver)—is invoked.

## Syntax

    observer.observe(options);

### Parameters

`options`  
A `PerformanceObserverInit` dictionary with the following possible members:

- `entryTypes`: An array of [`DOMString`](../domstring) objects, each specifying one performance entry type to observe. May not be used together with the "`type`" or "`buffered`" options.
- `type`: A single [`DOMString`](../domstring) specifying exactly one performance entry type to observe. May not be used together with the `entryTypes` option.
- `buffered`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag to indicate whether buffered entries should be queued into the observer's buffer. Must be used only with the "`type`" option.

See [`PerformanceEntry.entryType`](../performanceentry/entrytype) for a list of valid performance entry type names. Unrecognized types are ignored, though the browser may output a warning message to the console to help developers debug their code. If no valid types are found, `observe()` has no effect.

## Examples

This example creates and configures two `PerformanceObservers`; one watches for `"mark"` and `"frame"` events, and the other watches for `"measure"` events.

    var observer = new PerformanceObserver(function(list, obj) {
      var entries = list.getEntries();
      for (var i=0; i < entries.length; i++) {
        // Process "mark" and "frame" events
      }
    });
    observer.observe({entryTypes: ["mark", "frame"]});

    function perf_observer(list, observer) {
      // Process the "measure" event
    }
    var observer2 = new PerformanceObserver(perf_observer);
    observer2.observe({entryTypes: ["measure"]});

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/performance-timeline/#dom-performanceobserver-observe">Performance Timeline Level 2<br />
<span class="small">The definition of 'observe()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition of <code>observe()</code> method.</td></tr></tbody></table>

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

`observe`

52

≤79

57

No

39

11

52

52

57

41

11

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceObserver/observe" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceObserver/observe</a>
