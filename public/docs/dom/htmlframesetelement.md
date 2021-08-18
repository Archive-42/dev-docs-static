# HTMLFrameSetElement

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `HTMLFrameSetElement` interface provides special properties (beyond those of the regular [`HTMLElement`](htmlelement) interface they also inherit) for manipulating [`<frameset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frameset) elements.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement) and from [`WindowEventHandlers`](windoweventhandlers)._

<span class="page-not-created">`HTMLFrameSetElement.cols`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) structured as a comma-separated list specifying the width of each column inside a frameset.

<span class="page-not-created">`HTMLFrameSetElement.rows`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) structured as a comma-separated list specifying the height of each column inside a frameset.

## Methods

_No specific method; inherits methods from its parent, [`HTMLElement`](htmlelement) and from [`WindowEventHandlers`](windoweventhandlers)._

## Event handlers

_No specific event handler; inherits event handlers from its parent, [`HTMLElement`](htmlelement) and from [`WindowEventHandlers`](windoweventhandlers)._

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

<span class="page-not-created">`WindowEventHandlers.onresize`</span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `resize` event is raised.

[`WindowEventHandlers.onstorage`](windoweventhandlers/onstorage)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `storage` event is raised.

[`WindowEventHandlers.onunload`](windoweventhandlers/onunload)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `unload` event is raised.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlframesetelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLFrameSetElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>From the <a href="https://www.w3.org/TR/html52/">HTML5</a> snapshot, the <a href="windoweventhandlers"><code>WindowEventHandlers</code></a> interface now have a <code>onlanguagechange</code> property.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/obsolete.html#htmlframesetelement">HTML5<br />
<span class="small">The definition of 'HTMLFrameSetElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of a previous <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a><br />
Frames are now obsolete. Implements <a href="windoweventhandlers"><code>WindowEventHandlers</code></a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-ID-43829095">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLBodyElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-43829095">Document Object Model (DOM) Level 1 Specification<br />
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

`HTMLFrameSetElement`

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

`cols`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`event_handlers`

Yes

≤79

Yes

?

?

?

Yes

Yes

Yes

?

?

Yes

`onstorage`

3

12

45

9

15

4

≤37

18

45

14

3.2

1.0

`rows`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

## See also

- HTML element implementing this interface: [`<frameset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frameset)
- The equivalent of this element outside of frames: [`HTMLBodyElement`](htmlbodyelement).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFrameSetElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFrameSetElement</a>
