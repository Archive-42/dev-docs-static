# HTMLMediaElement.buffered

The `buffered` read-only property of [`HTMLMediaElement`](../htmlmediaelement) objects returns a new static [normalized `TimeRanges` object](../timeranges#normalized_timeranges_objects) that represents the ranges of the media resource, if any, that the user agent has buffered at the moment the `buffered` property is accessed.

**Note:** This feature is not available in [Web Workers](../web_workers_api).

## Syntax

    var timeRange = audioObject.buffered

### Value

A new static [normalized TimeRanges object](../timeranges#normalized_timeranges_objects) that represents the ranges of the media resource, if any, that the user agent has buffered at the moment the `buffered` property is accessed.

## Example

    var obj = document.createElement('video');
    console.log(obj.buffered); // TimeRanges { length: 0 }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#dom-media-buffered">HTML Living Standard<br />
<span class="small">The definition of 'buffered' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://w3c.github.io/media-source/#htmlmediaelement-extensions">Media Source Extensions</a></td><td><span class="spec-rec">Recommendation</span></td><td>Specifies a new algorithm for returning the buffered ranges of an element whose source is a <a href="../mediasource"><code>MediaSource</code></a> object.</td></tr></tbody></table>

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

`buffered`

43

12

4

9

≤12.1

3.2

43

43

4

≤12.1

3

4.0

## See also

- The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/buffered" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/buffered</a>
