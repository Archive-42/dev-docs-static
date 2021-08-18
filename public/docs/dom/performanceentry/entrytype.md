PerformanceEntry.entryType
==========================

The `entryType` property returns a [`DOMString`](../domstring) representing the type of performance metric such as, for example, "`mark`". This property is read only.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var type = entry.entryType;

### Return value

The return value depends on the subtype of the `PerformanceEntry` object and affects the value of the [`PerformanceEntry.name`](name) property as shown by the table below.

### Performance entry type names

<table><colgroup><col style="width: 25%" /><col style="width: 25%" /><col style="width: 25%" /><col style="width: 25%" /></colgroup><thead><tr class="header"><th>Value</th><th>Subtype</th><th>Type of name property</th><th>Description of name property</th></tr></thead><tbody><tr class="odd"><td><code>element</code></td><td><a href="../performanceelementtiming"><code>PerformanceElementTiming</code></a></td><td><a href="../domstring"><code>DOMString</code></a></td><td>Reports load time of elements.</td></tr><tr class="even"><td><code>frame</code>, <code>navigation</code></td><td><a href="../performanceframetiming"><code>PerformanceFrameTiming</code></a>, <a href="../performancenavigationtiming"><code>PerformanceNavigationTiming</code></a></td><td><a href="../url"><code>URL</code></a></td><td>The document's address.</td></tr><tr class="odd"><td><code>resource</code></td><td><a href="../performanceresourcetiming"><code>PerformanceResourceTiming</code></a></td><td><a href="../url"><code>URL</code></a></td><td>The resolved URL of the requested resource. This value doesn't change even if the request is redirected.</td></tr><tr class="even"><td><code>mark</code></td><td><a href="../performancemark"><code>PerformanceMark</code></a></td><td><a href="../domstring"><code>DOMString</code></a></td><td>The name used when the mark was created by calling <a href="../performance/mark"><code>performance.mark()</code></a>.</td></tr><tr class="odd"><td><code>measure</code></td><td><a href="../performancemeasure"><code>PerformanceMeasure</code></a></td><td><a href="../domstring"><code>DOMString</code></a></td><td>name used when the measure was created by calling <a href="../performance/measure"><code>performance.measure()</code></a>.</td></tr><tr class="even"><td><code>paint</code></td><td><a href="../performancepainttiming"><code>PerformancePaintTiming</code></a></td><td><a href="../domstring"><code>DOMString</code></a></td><td><p>Either <code>'first-paint'</code> or <code>'first-contentful-paint'</code>.</p></td></tr><tr class="odd"><td><code>longtask</code></td><td><a href="../performancelongtasktiming"><code>PerformanceLongTaskTiming</code></a></td><td><a href="../domstring"><code>DOMString</code></a></td><td>reports instances of long tasks</td></tr></tbody></table>

Example
-------

The following example shows the use of the `entryType` property.

    function run_PerformanceEntry() {

      // check for feature support before continuing
      if (performance.mark === undefined) {
        console.log("performance.mark not supported");
        return;
      }

      // Create a performance entry named "begin" via the mark() method
      performance.mark("begin");

      // Check the entryType of all the "begin" entries
      var entriesNamedBegin = performance.getEntriesByName("begin");
        for (var i=0; i < entriesNamedBegin.length; i++) {
          var typeOfEntry = entriesNamedBegin[i].entryType;
          console.log("Entry is type: " + typeOfEntry);
      }

    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/performance-timeline/#dom-performanceentry-entrytype">Performance Timeline Level 2<br />
<span class="small">The definition of 'entryType' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/performance-timeline/#dom-performanceentry-entrytype">Performance Timeline<br />
<span class="small">The definition of 'entryType' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`entryType`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceEntry/entryType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceEntry/entryType</a>
