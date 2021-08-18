PerformanceResourceTiming.toJSON()
==================================

The `toJSON()` method is a *serializer* that returns a JSON representation of the [`PerformanceResourceTiming`](../performanceresourcetiming) object.

Syntax
------

    json = resourcePerfEntry.toJSON();

### Arguments

None

### Return value

json  
A JSON object that is the serialization of the [`PerformanceResourceTiming`](../performanceresourcetiming) object as a map with entries from the closest inherited interface and with entries for each of the serializable attributes.

Example
-------

    // Get a resource performance entry
    var perfEntries = performance.getEntriesByType("resource");
    var entry = perfEntries[0];

    // Get the JSON and log it
    var json = entry.toJSON();
    var s = JSON.stringify(json);
    console.log("PerformanceEntry.toJSON = " + s);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/resource-timing-2/#dom-performanceresourcetiming-tojson">Resource Timing Level 2<br />
<span class="small">The definition of 'toJSON' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

43

≤18

40

No

30

11

43

43

42

30

11

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming/toJSON" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming/toJSON</a>
