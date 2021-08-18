# PerformanceEntry.name

The `name` property of the [`PerformanceEntry`](../performanceentry) interface returns a value that further specifies the value returned by the [`PerformanceEntry.entryType`](entrytype) property. This property is read only.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var name = entry.name;

### Return value

The return value depends on the subtype of the `PerformanceEntry` object and the value of [`PerformanceEntry.entryType`](entrytype), as shown by the table below.

<table><thead><tr class="header"><th>Value</th><th>Subtype</th><th>entryType values</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><a href="../url"><code>URL</code></a></td><td><a href="../performanceframetiming"><code>PerformanceFrameTiming</code></a>, <a href="../performancenavigationtiming"><code>PerformanceNavigationTiming</code></a></td><td><code>frame</code>, <code>navigation</code></td><td>The document's address.</td></tr><tr class="even"><td><a href="../url"><code>URL</code></a></td><td><a href="../performanceresourcetiming"><code>PerformanceResourceTiming</code></a></td><td><code>resource</code></td><td>The resolved URL of the requested resource. This value doesn't change even if the request is redirected.</td></tr><tr class="odd"><td><a href="../domstring"><code>DOMString</code></a></td><td><a href="../performancemark"><code>PerformanceMark</code></a></td><td><code>mark</code></td><td>The name used when the mark was created by calling <a href="../performance/mark"><code>performance.mark()</code></a>.</td></tr><tr class="even"><td><a href="../domstring"><code>DOMString</code></a></td><td><a href="../performancemeasure"><code>PerformanceMeasure</code></a></td><td><code>measure</code></td><td>name used when the measure was created by calling <a href="../performance/measure"><code>performance.measure()</code></a>.</td></tr><tr class="odd"><td><a href="../domstring"><code>DOMString</code></a></td><td><a href="../performancepainttiming"><code>PerformancePaintTiming</code></a></td><td><code>paint</code></td><td>Either <code>'first-paint'</code> or <code>'first-contentful-paint'</code>.</td></tr></tbody></table>

## Example

The following example shows the use of the `name` property.

    function run_PerformanceEntry() {
      log("PerformanceEntry support ...");

      if (performance.mark === undefined) {
        log("... performance.mark Not supported");
        return;
      }

      // Create some performance entries via the mark() method
      performance.mark("Begin");
      do_work(50000);
      performance.mark("End");

      // Use getEntries() to iterate through the each entry
      var p = performance.getEntries();
      for (var i=0; i < p.length; i++) {
        log("Entry[" + i + "]");
        check_PerformanceEntry(p[i]);
      }
    }
    function check_PerformanceEntry(obj) {
      var properties = ["name", "entryType", "startTime", "duration"];
      var methods = ["toJSON"];

      for (var i=0; i < properties.length; i++) {
        // check each property
        var supported = properties[i] in obj;
        if (supported)
          log("..." + properties[i] + " = " + obj[properties[i]]);
        else
          log("..." + properties[i] + " = Not supported");
      }
      for (var i=0; i < methods.length; i++) {
        // check each method
        var supported = typeof obj[methods[i]] == "function";
        if (supported) {
          var js = obj[methods[i]]();
          log("..." + methods[i] + "() = " + JSON.stringify(js));
        } else {
          log("..." + methods[i] + " = Not supported");
        }
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/performance-timeline/#dom-performanceentry-name">Performance Timeline Level 2<br />
<span class="small">The definition of 'name' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/performance-timeline/#dom-performanceentry-name">Performance Timeline<br />
<span class="small">The definition of 'name' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`name`

28

12

Yes

Yes

15

11

≤37

28

25

14

11

1.5

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceEntry/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceEntry/name</a>
