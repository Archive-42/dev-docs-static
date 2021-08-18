# performance.clearMarks()

The `clearMarks()` method removes the _named mark_ from the browser's performance entry buffer. If the method is called with no arguments, all [`performance entries`](../performanceentry) with an [`entry type`](../performanceentry/entrytype) of "`mark`" will be removed from the performance entry buffer.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    performance.clearMarks();
    performance.clearMarks(name);

### Arguments

name <span class="badge inline optional">Optional</span>  
A [`DOMString`](../domstring) representing the name of the timestamp. If this argument is omitted, all [`performance entries`](../performanceentry) with an [`entry type`](../performanceentry/entrytype) of "`mark`" will be removed.

### Return value

void

## Example

The following example shows both uses of the `clearMarks()` method.

    // Create a small helper to show how many PerformanceMark entries there are.
    function logMarkCount() {
      console.log(
        "Found this many entries: " + performance.getEntriesByType("mark").length
      );
    }

    // Create a bunch of marks.
    performance.mark("squirrel");
    performance.mark("squirrel");
    performance.mark("monkey");
    performance.mark("monkey");
    performance.mark("dog");
    performance.mark("dog");

    logMarkCount() // "Found this many entries: 6"

    // Delete just the "squirrel" PerformanceMark entries.
    performance.clearMarks('squirrel');
    logMarkCount() // "Found this many entries: 4"

    // Delete all of the PerformanceMark entries.
    performance.clearMarks();
    logMarkCount() // "Found this many entries: 0"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/user-timing/#dom-performance-clearmarks">User Timing Level 2<br />
<span class="small">The definition of 'clearMarks()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Clarifies <code>clearMarks()</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/user-timing/#dom-performance-clearmarks">User Timing<br />
<span class="small">The definition of 'clearMarks()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Basic definition.</td></tr></tbody></table>

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

`clearMarks`

29

25-29

12

41

10

33

11

≤37

29

25-29

42

33

11

2.0

1.5-2.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Performance/clearMarks" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Performance/clearMarks</a>
