# performance.now()

The `performance.now()` method returns a [`DOMHighResTimeStamp`](../domhighrestimestamp), measured in milliseconds.

**Note:** This feature is available in [Web Workers](../web_workers_api).

The returned value represents the time elapsed since the [time origin](../domhighrestimestamp#the_time_origin).

Bear in mind the following points:

- In dedicated workers created from a [`Window`](../window) context, the value in the worker will be lower than `performance.now()` in the window who spawned that worker. It used to be the same as `t0` of the main context, but this was changed.
- In shared or service workers, the value in the worker might be higher than that of the main context because that window can be created after those workers.

It's important to keep in mind that to mitigate potential security threats such as [Spectre](https://spectreattack.com/), browsers typically round the returned value by some amount in order to be less predictable. This inherently introduces a degree of inaccuracy by limiting the resolution or precision of the timer. For example, Firefox rounds the returned time to 1 millisecond increments.

The precision of the returned value is subject to change if/when the security concerns are alleviated through other means.

## Syntax

    t = performance.now();

## Example

    const t0 = performance.now();
    doSomething();
    const t1 = performance.now();
    console.log(`Call to doSomething took ${t1 - t0} milliseconds.`);

Unlike other timing data available to JavaScript (for example [`Date.now`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/now)), the timestamps returned by `performance.now()` are not limited to one-millisecond resolution. Instead, they represent times as floating-point numbers with up to microsecond precision.

Also unlike `Date.now()`, the values returned by `performance.now()` always increase at a constant rate, independent of the system clock (which might be adjusted manually or skewed by software like NTP). Otherwise, `performance.timing.navigationStart + performance.now()` will be approximately equal to `Date.now()`.

## Reduced time precision

To offer protection against timing attacks and fingerprinting, the precision of `performance.now()` might get rounded depending on browser settings.  
In Firefox, the `privacy.reduceTimerPrecision` preference is enabled by default and defaults to 1ms.

    // reduced time precision (1ms) in Firefox 60
    performance.now();
    // 8781416
    // 8781815
    // 8782206
    // ...

    // reduced time precision with `privacy.resistFingerprinting` enabled
    performance.now();
    // 8865400
    // 8866200
    // 8866700
    // ...

In Firefox, you can also enable `privacy.resistFingerprinting` — this changes the precision to 100ms or the value of `privacy.resistFingerprinting.reduceTimerPrecision.microseconds`, whichever is larger.

Starting with Firefox 79, high resolution timers can be used if you cross-origin isolate your document using the [`Cross-Origin-Opener-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cross-Origin-Opener-Policy) and [`Cross-Origin-Embedder-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cross-Origin-Embedder-Policy) headers:

    Cross-Origin-Opener-Policy: same-origin
    Cross-Origin-Embedder-Policy: require-corp

These headers ensure a top-level document does not share a browsing context group with cross-origin documents. COOP process-isolates your document and potential attackers can't access to your global object if they were opening it in a popup, preventing a set of cross-origin attacks dubbed [XS-Leaks](https://github.com/xsleaks/xsleaks).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/hr-time-2/#dom-performance-now">High Resolution Time Level 2<br />
<span class="small">The definition of 'performance.now()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Stricter definitions of interfaces and types.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/hr-time-1/#dom-performance-now">High Resolution Time<br />
<span class="small">The definition of 'performance.now()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`now`

24

21-24

12

15

\["In Firefox 57.0.4 the accuracy was reduced to 20 microseconds.", "In Firefox 59 the accuracy was reduced to 2 milliseconds.", "In Firefox 60 the accuracy was increased to 1 millisecond."\]

10

15

8

≤37

25

15

\["In Firefox 57.0.4 the accuracy was reduced to 20 microseconds.", "In Firefox 59 the accuracy was reduced to 2 milliseconds.", "In Firefox 60 the accuracy was increased to 1 millisecond."\]

14

9

1.5

## See also

- [When milliseconds are not enough: performance.now()](http://updates.html5rocks.com/2012/08/When-milliseconds-are-not-enough-performance-now) from HTML5 Rocks.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Performance/now" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Performance/now</a>
