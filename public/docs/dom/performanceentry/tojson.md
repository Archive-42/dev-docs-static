# PerformanceEntry.toJSON()

The `toJSON()` method is a _serializer_; it returns a JSON representation of the [`performance entry`](../performanceentry) object.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    json = perfEntry.toJSON();

### Arguments

None

### Return value

json  
A JSON object that is the serialization of the [`PerformanceEntry`](../performanceentry) object.

## Example

The following example shows the use of the `toJSON()` method.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/performance-timeline/#dom-performanceentry-tojson">Performance Timeline Level 2<br />
<span class="small">The definition of 'toJSON' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition of <code>toJSON()</code> method.</td></tr></tbody></table>

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

45

16

Yes

No

32

11

45

45

25

32

11

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceEntry/toJSON" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceEntry/toJSON</a>
