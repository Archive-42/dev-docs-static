# PerformanceNavigation.type

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Warning**

This interface of this property is deprecated in the [Navigation Timing Level 2 specification](https://w3c.github.io/navigation-timing/#obsolete). Please use the [`PerformanceNavigationTiming`](../performancenavigationtiming) interface instead.

The legacy ` PerformanceNavigation``.type ` read-only property returns an `unsigned short` containing a constant describing how the navigation to this page was done. Possible values are:

<table><thead><tr class="header"><th>Value</th><th>Constant name</th><th>Meaning</th></tr></thead><tbody><tr class="odd"><td><code>0</code></td><td><code>TYPE_NAVIGATE</code></td><td>The page was accessed by following a link, a bookmark, a form submission, a script, or typing the URL in the address bar.</td></tr><tr class="even"><td><code>1</code></td><td><code>TYPE_RELOAD</code></td><td>The page was accessed by clicking the Reload button or via the <a href="../location/reload"><code>Location.reload()</code></a> method.</td></tr><tr class="odd"><td><code>2</code></td><td><code>TYPE_BACK_FORWARD</code></td><td>The page was accessed by navigating into the history.</td></tr><tr class="even"><td><code>255</code></td><td><code>TYPE_RESERVED</code></td><td>Any other way.</td></tr></tbody></table>

## Syntax

    type = performanceNavigation.type;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/navigation-timing/#dom-performancenavigation-type">Navigation Timing<br />
<span class="small">The definition of 'PerformanceNavigation.type' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`type`

10

12

7

This property can return incorrect values. See [bug 1459711](https://bugzil.la/1459711).

9

15

8

≤37

18

7

This property can return incorrect values. See [bug 1459711](https://bugzil.la/1459711).

14

9

1.0

## See also

- The [`PerformanceNavigation`](../performancenavigation) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceNavigation/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceNavigation/type</a>
