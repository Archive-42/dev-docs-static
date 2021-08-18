# ByteLengthQueuingStrategy.size()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `size()` method of the [`ByteLengthQueuingStrategy`](../bytelengthqueuingstrategy) interface returns the given chunk’s `byteLength` property.

## Syntax

    var size = byteLengthQueuingStrategy.size(chunk);

### Parameters

chunk  
A chunk of data being passed through the stream.

### Return value

An integer representing the byte length of the given chunk.

## Examples

    const queuingStrategy = new ByteLengthQueuingStrategy({ highWaterMark: 1 });

    const readableStream = new ReadableStream({
      start(controller) {
        ...
      },
      pull(controller) {
        ...
      },
      cancel(err) {
        console.log("stream error:", err);
      }
    }, queuingStrategy);

    var size = queueingStrategy.size(chunk);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#blqs-size">Streams<br />
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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ByteLengthQueuingStrategy/size" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ByteLengthQueuingStrategy/size</a>
