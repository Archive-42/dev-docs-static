# PerformanceResourceTiming.initiatorType

The `initiatorType` read-only property is a [`string`](../domstring) that represents the _type_ of resource that initiated the performance event.

The value of this string is as follows:

- If the initiator is a [`Element`](../element), the property returns the element's [`localName`](../element/localname).
- If the initiator is a [`CSS`](../css) resource, the property returns "`css`".
- If the initiator is a [`XMLHttpRequest`](../xmlhttprequest) object, the property returns "`xmlhttprequest`".
- If the initiator is a [`PerformanceNavigationTiming`](../performancenavigationtiming) object, the property returns an empty string (`""`).

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    resource.initiatorType;

### Return value

A [`string`](../domstring) representing the _type_ of resource that initiated the performance event, as specified above.

## Example

    function print_PerformanceEntries() {
      // Use getEntriesByType() to just get the "resource" events
      var p = performance.getEntriesByType("resource");
      for (var i=0; i < p.length; i++) {
        print_initiatorType(p[i]);
      }
    }
    function print_initiatorType(perfEntry) {
      // Print this performance entry object's initiatorType value
      var value = "initiatorType" in perfEntry;
      if (value)
        console.log("... initiatorType = " + perfEntry.initiatorType);
      else
        console.log("... initiatorType = NOT supported");
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/resource-timing-1/#dom-performanceresourcetiming-initiatortype">Resource Timing Level 1<br />
<span class="small">The definition of 'initiatorType' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`initiatorType`

43

12

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming/initiatorType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming/initiatorType</a>
