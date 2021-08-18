# PerformanceNavigationTiming.domComplete

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `domComplete` read-only property returns a [`timestamp`](../domhighrestimestamp) representing the time value equal to the time immediately before the user agent sets the current document readiness of the current document to _[complete](https://html.spec.whatwg.org/multipage/syntax.html#the-end)_.

## Syntax

    perfEntry.domComplete;

### Return Value

A [`timestamp`](../domhighrestimestamp) representing a time value equal to the time immediately before the user agent sets the current document readiness of the current document to _[complete](https://html.spec.whatwg.org/multipage/syntax.html#the-end)_.

## Example

The following example illustrates this property's usage.

    function print_nav_timing_data() {
      // Use getEntriesByType() to just get the "navigation" events
      var perfEntries = performance.getEntriesByType("navigation");

      for (var i=0; i < perfEntries.length; i++) {
        console.log("= Navigation entry[" + i + "]");
        var p = perfEntries[i];
        // dom Properties
        console.log("DOM content loaded = " + (p.domContentLoadedEventEnd - p.domContentLoadedEventStart));
        console.log("DOM complete = " + p.domComplete);
        console.log("DOM interactive = " + p.interactive);

        // document load and unload time
        console.log("document load = " + (p.loadEventEnd - p.loadEventStart));
        console.log("document unload = " + (p.unloadEventEnd - p.unloadEventStart));

        // other properties
        console.log("type = " + p.type);
        console.log("redirectCount = " + p.redirectCount);
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/navigation-timing/#dom-performancenavigationtiming-domcomplete">Navigation Timing Level 2<br />
<span class="small">The definition of 'domComplete' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`domComplete`

57

12

58

No

44

No

57

57

58

43

No

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceNavigationTiming/domComplete" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceNavigationTiming/domComplete</a>
