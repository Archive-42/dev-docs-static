# PerformanceTiming.redirectEnd

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Warning**

This interface of this property is deprecated in the [Navigation Timing Level 2 specification](https://w3c.github.io/navigation-timing/#obsolete). Please use the [`PerformanceNavigationTiming`](../performancenavigationtiming) interface instead.

The legacy ` PerformanceTiming``.redirectEnd ` read-only property returns an `unsigned long long` representing the moment, in milliseconds since the UNIX epoch, the last HTTP redirect is completed, that is when the last byte of the HTTP response has been received. If there is no redirect, or if one of the redirect is not of the same origin, the value returned is `0`.

## Syntax

    time = performanceTiming.redirectEnd;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/navigation-timing/#dom-performancetiming-redirectend">Navigation Timing<br />
<span class="small">The definition of 'PerformanceTiming.redirectEnd' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`redirectEnd`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

## See also

- The [`Performance`](../performance) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming/redirectEnd" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming/redirectEnd</a>
