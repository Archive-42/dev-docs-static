# PerformanceNavigation

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Warning**

This interface is deprecated in the [Navigation Timing Level 2 specification](https://w3c.github.io/navigation-timing/#obsolete). Please use the [`PerformanceNavigationTiming`](performancenavigationtiming) interface instead.

The legacy `PerformanceNavigation` interface represents information about how the navigation to the current document was done.

An object of this type can be obtained by calling the [`Performance.navigation`](performance/navigation) read-only attribute.

## Properties

_The `PerformanceNavigation` interface doesn't inherit any properties._

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceNavigation.type`](performancenavigation/type) <span class="badge inline readonly">Read only </span>  
An `unsigned short` which indicates how the navigation to this page was done. Possible values are:

`TYPE_NAVIGATE` (0)  
The page was accessed by following a link, a bookmark, a form submission, or a script, or by typing the URL in the address bar.

`TYPE_RELOAD` (1)  
The page was accessed by clicking the Reload button or via the [`Location.reload()`](location/reload) method.

`TYPE_BACK_FORWARD` (2)  
The page was accessed by navigating into the history.

`TYPE_RESERVED` (255)  
Any other way.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceNavigation.redirectCount`](performancenavigation/redirectcount) <span class="badge inline readonly">Read only </span>  
An `unsigned short` representing the number of REDIRECTs done before reaching the page.

## Methods

_The `Performance` interface doesn't inherit any methods._

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="page-not-created">`PerformanceNavigation.toJSON()`</span>  
Is a jsonizer returning a json object representing the `PerformanceNavigation` object.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/navigation-timing/#performancenavigation">Navigation Timing<br />
<span class="small">The definition of 'PerformanceNavigation' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PerformanceNavigation`

10

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

`redirectCount`

10

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

`toJSON`

56

12

25

This property can return incorrect values. See [bug 1459711](https://bugzil.la/1459711).

9

43

14.1

56

56

25

This property can return incorrect values. See [bug 1459711](https://bugzil.la/1459711).

43

14.5

6.0

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

- The [`Performance`](performance) that allows access to an object of this type.
- [`PerformanceNavigationTiming`](performancenavigationtiming) (part of Navigation Timing Level 2) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceNavigation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceNavigation</a>
