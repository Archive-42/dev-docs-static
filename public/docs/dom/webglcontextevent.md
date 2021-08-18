WebGLContextEvent
=================

The **WebContextEvent** interface is part of the [WebGL API](webgl_api) and is an interface for an event that is generated in response to a status change to the WebGL rendering context.

Inheritance
-----------

*This interface inherits properties and methods from its parent interface, [`Event`](event).*

Properties
----------

*This interface inherits properties from its parent interface, [`Event`](event).*

[`WebGLContextEvent.statusMessage`](webglcontextevent/statusmessage)  
A read-only property containing additional information about the event.

Methods
-------

*This interface doesn't define any own methods, but inherits methods from its parent interface, [`Event`](event).*

Examples
--------

With the help of the [`WEBGL_lose_context`](webgl_lose_context) extension, you can simulate the `webglcontextlost` and `webglcontextrestored` events:

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');

    canvas.addEventListener('webglcontextlost', function(e) {
      console.log(e);
    }, false);

    gl.getExtension('WEBGL_lose_context').loseContext();

    // WebGLContextEvent event with type "webglcontextlost" is logged.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.15">WebGL 1.0<br />
<span class="small">The definition of 'WebGLContextEvent' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WebGLContextEvent`

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

`worker_support`

No

No

49

No

No

No

No

No

No

No

No

No

See also
--------

-   [`WebGLRenderingContext.isContextLost()`](webglrenderingcontext/iscontextlost)
-   [`WEBGL_lose_context`](webgl_lose_context), [`WEBGL_lose_context.loseContext()`](webgl_lose_context/losecontext), [`WEBGL_lose_context.restoreContext()`](webgl_lose_context/restorecontext)
-   Events: [webglcontextlost](htmlcanvaselement/webglcontextlost_event), [webglcontextrestored](htmlcanvaselement/webglcontextrestored_event), [webglcontextcreationerror](htmlcanvaselement/webglcontextcreationerror_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLContextEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLContextEvent</a>
