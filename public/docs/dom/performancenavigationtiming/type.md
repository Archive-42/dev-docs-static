# PerformanceNavigationTiming.type

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `type` read-only property returns a [`string`](../domstring) representing the type of navigation. The value must be one of the following:

navigate  
Navigation started by clicking a link, entering the URL in the browser's address bar, form submission, or initializing through a script operation other than reload and back_forward as listed below.

reload  
Navigation is through the browser's reload operation or [`location.reload()`](../location/reload).

back_forward  
Navigation is through the browser's history traversal operation.

prerender  
Navigation is initiated by a [prerender hint](https://www.w3.org/TR/resource-hints/#prerender).

This property is <span class="badge inline readonly">Read only </span>.

## Syntax

    perfEntry.type;

### Return Value

A [`string`](../domstring) which is one of the values listed above.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/navigation-timing/#dom-performancenavigationtiming-type">Navigation Timing Level 2<br />
<span class="small">The definition of 'type' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceNavigationTiming/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceNavigationTiming/type</a>
