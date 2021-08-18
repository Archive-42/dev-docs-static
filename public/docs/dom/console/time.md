# Console.time()

Starts a timer you can use to track how long an operation takes. You give each timer a unique name, and may have up to 10,000 timers running on a given page. When you call [`console.timeEnd()`](timeend) with the same name, the browser will output the time, in milliseconds, that elapsed since the timer was started.

See [Timers](../console#timers) in the [`console`](../console) documentation for details and examples.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    console.time(label);

## Parameters

`label`  
The name to give the new timer. This will identify the timer; use the same name when calling [`console.timeEnd()`](timeend) to stop the timer and get the time output to the console.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://console.spec.whatwg.org/#time">Console API<br />
<span class="small">The definition of 'console.time()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`time`

1

12

10

11

11

4

1

18

10

11

3.2

1.0

## See also

- [`Console.timeEnd()`](timeend)
- [`Console.timeLog()`](timelog)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Console/time" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Console/time</a>
