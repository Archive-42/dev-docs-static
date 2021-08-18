# performance.mark()

The `mark()` method creates a [`timestamp`](../domhighrestimestamp) in the browser's _performance entry buffer_ with the given name.

The application defined timestamp can be retrieved by one of the [`Performance`](../performance) interface's `getEntries*()` methods ([`getEntries()`](getentries), [`getEntriesByName()`](getentriesbyname) or [`getEntriesByType()`](getentriesbytype)).

The `mark()'s` stores its data internally as [`PerformanceEntry`](../performanceentry).

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    performance.mark(name);

### Arguments

name  
A [`DOMString`](../domstring) representing the name of the mark. If the `name` given to this method already exists in the [`PerformanceTiming`](../performancetiming) interface, [`SyntaxError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SyntaxError) is thrown.

### Return value

void

## Example

The following example shows how to use `mark()` to create and retrieve [`PerformanceMark`](../performancemark) entries.

    // Create a bunch of marks.
    performance.mark("squirrel");
    performance.mark("squirrel");
    performance.mark("monkey");
    performance.mark("monkey");
    performance.mark("dog");
    performance.mark("dog");

    // Get all of the PerformanceMark entries.
    const allEntries = performance.getEntriesByType("mark");
    console.log(allEntries.length);
    // 6

    // Get all of the "monkey" PerformanceMark entries.
    const monkeyEntries = performance.getEntriesByName("monkey");
    console.log(monkeyEntries.length);
    // 2

    // Clear out all of the marks.
    performance.clearMarks();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/user-timing/#dom-performance-mark">User Timing Level 2<br />
<span class="small">The definition of 'mark()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Clarifies <code>mark()</code> processing model.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/user-timing/#dom-performance-mark">User Timing<br />
<span class="small">The definition of 'mark()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Basic definition.</td></tr></tbody></table>

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

`mark`

28

25-28

12

41

10

33

11

≤37

28

25-28

42

33

11

1.5

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Performance/mark" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Performance/mark</a>
