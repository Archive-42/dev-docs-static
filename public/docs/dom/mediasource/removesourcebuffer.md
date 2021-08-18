# MediaSource.removeSourceBuffer()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `removeSourceBuffer()` method of the [`MediaSource`](../mediasource) interface removes the given [`SourceBuffer`](../sourcebuffer) from the <span class="page-not-created">`SourceBuffers`</span> list associated with this `MediaSource` object.

## Syntax

    mediaSource.removeSourceBuffer(sourceBuffer);

### Parameters

sourceBuffer  
The [`SourceBuffer`](../sourcebuffer) object to be removed.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

### Exceptions

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>NotFoundError</code></td><td>The supplied sourceBuffer doesn't exist in <a href="sourcebuffers"><code>MediaSource.sourceBuffers</code></a>.</td></tr></tbody></table>

## Examples

    for (i = 0; i < 10; i++) {
      var sourceBuffer = mediaSource.addSourceBuffer(mimeCodec);
    }

    mediaSource.removeSourceBuffer(mediaSource.sourceBuffers[0]);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#dom-mediasource-removesourcebuffer">Media Source Extensions<br />
<span class="small">The definition of 'removeSourceBuffer()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`removeSourceBuffer`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

25

41

14

No

1.5

## See also

- [`SourceBuffer`](../sourcebuffer)
- [`SourceBufferList`](../sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSource/removeSourceBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSource/removeSourceBuffer</a>
