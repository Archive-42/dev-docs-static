# PerformanceNavigationTiming.toJSON()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `toJSON()` method is a _serializer_ - it returns a JSON representation of the [`PerformanceNavigationTiming`](../performancenavigationtiming) object.

## Syntax

    json = resourcePerfEntry.toJSON();

### Arguments

None

### Return value

json  
A JSON object that is the serialization of the [`PerformanceNavigationTiming`](../performancenavigationtiming) object as a map with entries from the closest inherited interface and with entries for each of the serializable attributes.

## Example

    // Get a resource performance entry
    var perfEntries = performance.getEntriesByType("navigation");
    var entry = perfEntries[0];

    // Get the JSON and log it
    var json = entry.toJSON();
    var s = JSON.stringify(json);
    console.log("PerformanceNavigationTiming.toJSON() = " + s);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/navigation-timing/#dom-performancenavigationtiming-tojson">Navigation Timing Level 2<br />
<span class="small">The definition of 'toJSON()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`toJSON`

57

≤18

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceNavigationTiming/toJSON" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceNavigationTiming/toJSON</a>
