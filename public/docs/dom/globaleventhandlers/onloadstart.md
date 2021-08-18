# GlobalEventHandlers.onloadstart

The `onloadstart` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `loadstart` event is raised (when progress has begun on the loading of a resource.)

## Syntax

    img.onloadstart = funcRef;

### Value

`funcRef` is the handler function to be called when the resource's `loadstart` event fires.

## Examples

### HTML content

    <img src="myImage.jpg">

### JavaScript content

    // 'loadstart' fires first, then 'load', then 'loadend'

    image.addEventListener('load', function(e) {
      console.log('Image loaded');
    });

    image.addEventListener('loadstart', function(e) {
      console.log('Image load started');
    });

    image.addEventListener('loadend', function(e) {
      console.log('Image load finished');
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onloadstart">HTML Living Standard<br />
<span class="small">The definition of 'onloadstart' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`onloadstart`

32

The `loadstart` event is not fired on `<img>` elements.

12

9

9

19

The `loadstart` event is not fired on `<img>` elements.

≤12.1-15

9

The `loadstart` event is not fired on `<img>` elements.

4.4.3

The `loadstart` event is not fired on `<img>` elements.

32

The `loadstart` event is not fired on `<img>` elements.

9

19

The `loadstart` event is not fired on `<img>` elements.

≤12.1-14

9

The `loadstart` event is not fired on `<img>` elements.

2.0

The `loadstart` event is not fired on `<img>` elements.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadstart" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadstart</a>
