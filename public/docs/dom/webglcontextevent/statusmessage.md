WebGLContextEvent.statusMessage
===============================

The read-only `WebGLContextEvent.statusMessage` property contains additional event status information, or is an empty string if no additional information is available.

Examples
--------

The `statusMessage` property can contain a platform dependent string with details of an event. This can occur, for example, if the `webglcontextcreationerror` event is fired.

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');

    canvas.addEventListener('webglcontextcreationerror', function(e) {
      console.log('WebGL context creation failed:' +
                  e.statusMessage || 'Unknown error');
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.15.1">WebGL 1.0<br />
<span class="small">The definition of 'WebGLContextEvent.statusMessage' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`statusMessage`

9

12

49

11

12

5.1

≤37

25

49

12

8

1.5

See also
--------

-   [webglcontextcreationerror](../htmlcanvaselement/webglcontextcreationerror_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLContextEvent/statusMessage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLContextEvent/statusMessage</a>
