# PerformanceNavigationTiming.redirectCount

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `redirectCount` property returns a [`timestamp`](../domhighrestimestamp) representing the number of redirects since the last non-redirect navigation under the current browsing context.

This property is <span class="badge inline readonly">Read only </span>.

## Syntax

    perfEntry.redirectCount;

### Return Value

A number representing the number of redirects since the last non-redirect navigation under the current browsing context.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/navigation-timing/#dom-performancenavigationtiming-redirectcount">Navigation Timing Level 2<br />
<span class="small">The definition of 'redirectCount' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`redirectCount`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceNavigationTiming/redirectCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceNavigationTiming/redirectCount</a>
