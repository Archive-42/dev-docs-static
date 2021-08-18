WindowEventHandlers
===================

The `WindowEventHandlers` mixin describes the event handlers common to several interfaces like [`Window`](window), or [`HTMLBodyElement`](htmlbodyelement) and [`HTMLFrameSetElement`](htmlframesetelement). Each of these interfaces can implement additional specific event handlers.

**Note**: `WindowEventHandlers` is a mixin and not an interface; you can't actually create an object of type `WindowEventHandlers`.

Properties
----------

*The events properties, of the form `onXYZ`, are defined on the [`WindowEventHandlers`](windoweventhandlers), and implemented by [`Window`](window), and [`WorkerGlobalScope`](workerglobalscope) for Web Workers.*

[`WindowEventHandlers.onafterprint`](windoweventhandlers/onafterprint)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `afterprint` event is raised.

[`WindowEventHandlers.onbeforeprint`](windoweventhandlers/onbeforeprint)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `beforeprint` event is raised.

[`WindowEventHandlers.onbeforeunload`](windoweventhandlers/onbeforeunload)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `beforeunload` event is raised.

[`WindowEventHandlers.onhashchange`](windoweventhandlers/onhashchange)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `hashchange` event is raised.

 [`WindowEventHandlers.onlanguagechange`](windoweventhandlers/onlanguagechange) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `languagechange` event is raised.

[`WindowEventHandlers.onmessage`](windoweventhandlers/onmessage)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `message` event is raised.

[`WindowEventHandlers.onmessageerror`](windoweventhandlers/onmessageerror)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `MessageError` event is raised.

<span class="page-not-created">`WindowEventHandlers.onoffline`</span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `offline` event is raised.

<span class="page-not-created">`WindowEventHandlers.ononline`</span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `online` event is raised.

<span class="page-not-created">`WindowEventHandlers.onpagehide`</span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `pagehide` event is raised.

<span class="page-not-created">`WindowEventHandlers.onpageshow`</span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `pageshow` event is raised.

[`WindowEventHandlers.onpopstate`](windoweventhandlers/onpopstate)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `popstate` event is raised.

[`WindowEventHandlers.onrejectionhandled`](windoweventhandlers/onrejectionhandled)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `rejectionhandled` event is raised, indicating that a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) was rejected and the rejection has been handled.

[`WindowEventHandlers.onstorage`](windoweventhandlers/onstorage)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `storage` event is raised.

[`WindowEventHandlers.onunhandledrejection`](windoweventhandlers/onunhandledrejection)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `unhandledrejection` event is raised, indicating that a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) was rejected but the rejection was not handled.

[`WindowEventHandlers.onunload`](windoweventhandlers/onunload)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `unload` event is raised.

Methods
-------

*This interface defines no method.*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#windoweventhandlers">HTML Living Standard<br />
<span class="small">The definition of 'WindowEventHandlers' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change since the latest snapshot, <a href="https://www.w3.org/TR/html51/">HTML 5.1</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/#windoweventhandlers">HTML 5.1<br />
<span class="small">The definition of 'WindowEventHandlers' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>. Added <code>onlanguage</code> since the <a href="https://www.w3.org/TR/html52/">HTML5</a> snapshot.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/#windoweventhandlers">HTML5<br />
<span class="small">The definition of 'WindowEventHandlers' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>. Creation of <code>WindowEventHandlers</code> (properties where on the target before it).</td></tr></tbody></table>

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

`WindowEventHandlers`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`onafterprint`

63

12

6

Yes

50

13

63

63

?

46

13

8.0

`onbeforeprint`

63

12

6

Yes

50

13

63

63

?

46

13

8.0

`onbeforeunload`

1

12

1

4

12

3

1

18

4

12

1

1.0

`onhashchange`

5

12

3.6

8

10

5

≤37

18

4

10.1

5

1.0

`onlanguagechange`

37

≤79

32

No

24

?

37

37

4

24

?

4.0

`onmessage`

60

≤79

?

?

47

?

60

60

?

44

?

8.0

`onmessageerror`

60

≤79

57

?

47

?

60

60

57

44

?

8.0

`onpopstate`

5

12

4

10

11.5

6

37

18

4

11.5

5.1

1.0

`onrejectionhandled`

49

≤79

69

68

55

This event handler was added in Firefox 55 but was disabled since it wasn't fully implemented. It was fully implemented in Firefox 68 and enabled by default in Firefox 69.

No

36

11

49

49

68

55

This event handler was added in Firefox 55 but was disabled since it wasn't fully implemented. It was fully implemented in Firefox 68 but not enabled by default.

No

11.3

5.0

`onstorage`

1

≤18

45

?

15

?

≤37

18

45

14

?

1.0

`onunhandledrejection`

49

79

69

68

55

This event handler was added in Firefox 55 but was disabled since it wasn't fully implemented. It was fully implemented in Firefox 68 and enabled by default in Firefox 69.

No

36

11

49

49

68

55

This event handler was added in Firefox 55 but was disabled since it wasn't fully implemented. It was fully implemented in Firefox 68 but not enabled by default.

No

11.3

5.0

`onunload`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Window`](window) and [`WorkerGlobalScope`](workerglobalscope)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers</a>
