# CountQueuingStrategy.size()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `size()` method of the [`CountQueuingStrategy`](../countqueuingstrategy) interface always returns `1`, so that the total queue size is a count of the number of chunks in the queue.

## Syntax

    var size = countQueuingStrategy.size();

### Parameters

None.

### Return value

`1`.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#cqs-size">Streams<br />
<span class="small">The definition of 'size' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`size`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CountQueuingStrategy/size" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CountQueuingStrategy/size</a>
