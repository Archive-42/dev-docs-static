# CountQueuingStrategy.CountQueuingStrategy()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CountQueuingStrategy()` constructor creates and returns a `CountQueuingStrategy` object instance.

## Syntax

    var countQueuingStrategy = new CountQueuingStrategy({highWaterMark});

### Parameters

{highWaterMark}  
An object containing a `highWaterMark` property. This is a non-negative integer defining the total number of chunks that can be contained in the internal queue before backpressure is applied.

### Return value

An instance of the [`CountQueuingStrategy`](../countqueuingstrategy) object.

### Exceptions

None.

## Examples

    const queuingStrategy = new CountQueuingStrategy({ highWaterMark: 1 });

    const writableStream = new WritableStream({
      // Implement the sink
      write(chunk) {
        ...
      },
      close() {
        ...
      },
      abort(err) {
        console.log("Sink error:", err);
      }
    }, queuingStrategy);

    var size = queuingStrategy.size();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#cqs-constructor">Streams<br />
<span class="small">The definition of 'CountQueuingStrategy()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CountQueuingStrategy`

59

16

65

No

46

10.1

59

59

65

43

10.3

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CountQueuingStrategy/CountQueuingStrategy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CountQueuingStrategy/CountQueuingStrategy</a>
