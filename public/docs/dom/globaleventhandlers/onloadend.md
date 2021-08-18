GlobalEventHandlers.onloadend
=============================

The `onloadend` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `loadend` event is raised (when progress has stopped on the loading of a resource.)

Syntax
------

    img.onloadend = funcRef;

### Value

`funcRef` is the handler function to be called when the resource's `loadend` event fires.

Examples
--------

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

Browser compatibility
---------------------

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

`onloadend`

No

No

52

No

No

?

No

No

52

No

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadend" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onloadend</a>
