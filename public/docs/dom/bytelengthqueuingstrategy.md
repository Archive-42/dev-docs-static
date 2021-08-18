# ByteLengthQueuingStrategy

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `ByteLengthQueuingStrategy` interface of the [Streams API](streams_api) provides a built-in byte length queuing strategy that can be used when constructing streams.

## Constructor

[`ByteLengthQueuingStrategy()`](bytelengthqueuingstrategy/bytelengthqueuingstrategy)  
Creates a new `ByteLengthQueuingStrategy` object instance.

## Properties

None.

## Methods

[`ByteLengthQueuingStrategy.size()`](bytelengthqueuingstrategy/size)  
Returns the given chunk’s `byteLength` property.

## Examples

    const queueingStrategy = new ByteLengthQueuingStrategy({ highWaterMark: 1 });

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
    }, queueingStrategy);

    var size = queueingStrategy.size(chunk);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#blqs-class">Streams<br />
<span class="small">The definition of 'ByteLengthQueuingStrategy' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ByteLengthQueuingStrategy`

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

`ByteLengthQueuingStrategy`

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

`highWaterMark`

78

16

65

The property is defined on the instance instead of the prototype object. See [bug 1684316](https://bugzil.la/1684316)

No

65

No

78

78

65

The property is defined on the instance instead of the prototype object. See [bug 1684316](https://bugzil.la/1684316)

56

No

12.0

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ByteLengthQueuingStrategy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ByteLengthQueuingStrategy</a>
