# HTMLBodyElement

The `HTMLBodyElement` interface provides special properties (beyond those inherited from the regular [`HTMLElement`](htmlelement) interface) for manipulating [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) elements.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement) and from [`WindowEventHandlers`](windoweventhandlers)._

<span class="page-not-created">`HTMLBodyElement.aLink`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) that represents the color of active hyperlinks.

<span class="page-not-created">`HTMLBodyElement.background`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) that represents the description of the location of the background image resource. Note that this is not an URI, though some older version of some browsers do expect it.

<span class="page-not-created">`HTMLBodyElement.bgColor`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) that represents the background color for the document.

<span class="page-not-created">`HTMLBodyElement.link`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) that represents the color of unvisited links.

<span class="page-not-created">`HTMLBodyElement.text`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) that represents the foreground color of text.

<span class="page-not-created">`HTMLBodyElement.vLink`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) that represents the color of visited links.

## Methods

_No specific methods; inherits methods from its parent, [`HTMLElement`](htmlelement), and from [`WindowEventHandlers`](windoweventhandlers)._

## Event handlers

_No specific event handlers; inherits event handlers from its parent, [`HTMLElement`](htmlelement) and from [`WindowEventHandlers`](windoweventhandlers)._

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
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called whenever an object receives a `message` event.

[`WindowEventHandlers.onmessageerror`](windoweventhandlers/onmessageerror)  
Is an [`eventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called whenever an object receives a `messageerror` event.

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
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code executed when the `rejectionhandled` event is raised, indicating that a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) was rejected and the rejection has been handled.

[`GlobalEventHandlers.onresize`](globaleventhandlers/onresize)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `resize` event is raised.

[`WindowEventHandlers.onstorage`](windoweventhandlers/onstorage)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `storage` event is raised.

[`WindowEventHandlers.onunhandledrejection`](windoweventhandlers/onunhandledrejection)  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code executed when the `unhandledrejection` event is raised, indicating that a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) was rejected but the rejection was not handled.

[`WindowEventHandlers.onunload`](windoweventhandlers/onunload)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `unload` event is raised.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlbodyelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLBodyElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Technically, the event-related properties <code>onafterprint</code>, <code>onbeforeprint</code>, <code>onbeforeunload</code>, <code>onblur</code>, <code>onerror</code>, <code>onfocus</code>, <code>onhashchange</code>, <code>onlanguagechange</code>, <code>onload</code>, <code>onmessage</code>, <code>onoffline</code>, <code>ononline</code>, <code>onpopstate</code>, <code>onresize</code>, <code>onstorage</code>, and <code>onunload</code>, have been moved to <a href="windoweventhandlers"><code>WindowEventHandlers</code></a>. <code>HTMLBodyElement</code> implements this interface.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/sections.html#the-body-element">HTML 5.1<br />
<span class="small">The definition of 'HTMLBodyElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/sections.html#the-body-element">HTML5<br />
<span class="small">The definition of 'HTMLBodyElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The following properties are now obsolete: <code>aLink</code>, <code>bgColor</code>, <code>background</code>, <code>link</code>, <code>text</code>, and <code>vLink</code>.<br />
The following properties have been added: <code>onafterprint</code>, <code>onbeforeprint</code>, <code>onbeforeunload</code>, <code>onblur</code>, <code>onerror</code>, <code>onfocus</code>, <code>onhashchange</code>, <code>onload</code>, <code>onmessage</code>, <code>onoffline</code>, <code>ononline</code>, <code>onpopstate</code>, <code>onresize</code>, <code>onstorage</code>, and <code>onunload</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-62018039">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLBodyElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-62018039">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLBodyElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLBodyElement`

1

12

1

4

≤12.1

3

1

18

4

≤12.1

1

1.0

`aLink`

1

12

1

4

≤12.1

3

1

18

4

≤12.1

1

1.0

`background`

1

12

1

4

≤12.1

3

1

18

4

≤12.1

1

1.0

`bgColor`

1

12

1

4

≤12.1

3

1

18

4

≤12.1

1

1.0

`link`

1

12

1

4

≤12.1

3

1

18

4

≤12.1

1

1.0

`onorientationchange`

No

No

No

No

No

No

Yes

Yes

No

Yes

Yes

Yes

`text`

1

12

1

4

≤12.1

3

1

18

4

≤12.1

1

1.0

`vLink`

1

12

1

4

≤12.1

3

1

18

4

≤12.1

1

1.0

## See also

- HTML element implementing this interface: [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body)
- [`WindowEventHandlers`](windoweventhandlers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLBodyElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLBodyElement</a>
