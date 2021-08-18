# Document

The `Document` interface represents any web page loaded in the browser and serves as an entry point into the web page's content, which is the [DOM tree](document_object_model/using_the_w3c_dom_level_1_core). The DOM tree includes elements such as [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) and [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table), among [many others](https://developer.mozilla.org/en-US/docs/Web/HTML/Element). It provides functionality globally to the document, like how to obtain the page's URL and create new elements in the document.

The `Document` interface describes the common properties and methods for any kind of document. Depending on the document's type (e.g. [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML), [XML](https://developer.mozilla.org/en-US/docs/Web/XML), SVG, …), a larger API is available: HTML documents, served with the `"text/html"` content type, also implement the [`HTMLDocument`](htmldocument) interface, whereas XML and SVG documents implement the [`XMLDocument`](xmldocument) interface.

## Constructor

[`Document()`](document/document)  
Creates a new `Document` object.

## Properties

_This interface also inherits from the [`Node`](node) and [`EventTarget`](eventtarget) interfaces._

[`Document.activeElement`](document/activeelement) <span class="badge inline readonly">Read only </span>  
Returns the [`Element`](element) that currently has focus.

[`Document.body`](document/body)  
Returns the [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) or [`<frameset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frameset) node of the current document.

[`Document.characterSet`](document/characterset)<span class="badge inline readonly">Read only </span>  
Returns the character set being used by the document.

[`Document.childElementCount`](document/childelementcount) <span class="badge inline readonly">Read only </span>  
Returns the number of child elements of the current document.

[`Document.children`](document/children) <span class="badge inline readonly">Read only </span>  
Returns the child elements of the current document.

[`Document.compatMode`](document/compatmode) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>  
Indicates whether the document is rendered in _quirks_ or _strict_ mode.

[`Document.contentType`](document/contenttype) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>  
Returns the Content-Type from the MIME Header of the current document.

[`Document.doctype`](document/doctype)<span class="badge inline readonly">Read only </span>  
Returns the Document Type Definition (DTD) of the current document.

[`Document.documentElement`](document/documentelement)<span class="badge inline readonly">Read only </span>  
Returns the [`Element`](element) that is a direct child of the document. For HTML documents, this is normally the [`HTMLHtmlElement`](htmlhtmlelement) object representing the document's [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) element.

[`Document.documentURI`](document/documenturi)<span class="badge inline readonly">Read only </span>  
Returns the document location as a string.

[`Document.embeds`](document/embeds)<span class="badge inline readonly">Read only </span>  
Returns a list of the embedded [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed) elements within the current document.

[`Document.firstElementChild`](document/firstelementchild) <span class="badge inline readonly">Read only </span>  
Returns the first child element of the current document.

[`Document.fonts`](document/fonts)  
Returns the [`FontFaceSet`](fontfaceset) interface of the current document.

[`Document.forms`](document/forms)<span class="badge inline readonly">Read only </span>  
Returns a list of the [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) elements within the current document.

[`Document.fullscreenElement`](document/fullscreenelement) <span class="badge inline readonly">Read only </span>  
The element that's currently in full screen mode for this document.

[`Document.head`](document/head)<span class="badge inline readonly">Read only </span>  
Returns the [`<head>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head) element of the current document.

[`Document.hidden`](document/hidden)<span class="badge inline readonly">Read only </span>  
Returns a Boolean value indicating if the page is considered hidden or not.

[`Document.images`](document/images)<span class="badge inline readonly">Read only </span>  
Returns a list of the images in the current document.

[`Document.implementation`](document/implementation)<span class="badge inline readonly">Read only </span>  
Returns the DOM implementation associated with the current document.

[`Document.lastElementChild`](document/lastelementchild) <span class="badge inline readonly">Read only </span>  
Returns the last child element of the current document.

[`Document.links`](document/links)<span class="badge inline readonly">Read only </span>  
Returns a list of all the hyperlinks in the document.

[`Document.mozSyntheticDocument`](document/mozsyntheticdocument) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` only if this document is synthetic, such as a standalone image, video, audio file, or the like.

[`Document.pictureInPictureElement`](document/pictureinpictureelement) <span class="badge inline readonly">Read only </span>  
Returns the [`Element`](element) currently being presented in picture-in-picture mode in this document.

[`Document.pictureInPictureEnabled`](document/pictureinpictureenabled) <span class="badge inline readonly">Read only </span>  
Returns true if the picture-in-picture feature is enabled.

[`Document.plugins`](document/plugins)<span class="badge inline readonly">Read only </span>  
Returns a list of the available plugins.

[`Document.pointerLockElement`](document/pointerlockelement) <span class="badge inline readonly">Read only </span>  
Returns the element set as the target for mouse events while the pointer is locked. `null` if lock is pending, pointer is unlocked, or if the target is in another document.

[`Document.featurePolicy`](document/featurepolicy) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>  
Returns the [`FeaturePolicy`](featurepolicy) interface which provides a simple API for introspecting the feature policies applied to a specific document.

[`Document.scripts`](document/scripts)<span class="badge inline readonly">Read only </span>  
Returns all the [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) elements on the document.

[`Document.scrollingElement`](document/scrollingelement)<span class="badge inline readonly">Read only </span>  
Returns a reference to the [`Element`](element) that scrolls the document.

[`Document.styleSheets`](document/stylesheets) <span class="badge inline readonly">Read only </span>  
Returns a [`StyleSheetList`](stylesheetlist) of [`CSSStyleSheet`](cssstylesheet) objects for stylesheets explicitly linked into, or embedded in a document.

[`Document.timeline`](document/timeline) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>  
Returns timeline as a special instance of [`DocumentTimeline`](documenttimeline) that is automatically created on page load.

[`Document.visibilityState`](document/visibilitystate)<span class="badge inline readonly">Read only </span>  
Returns a `string` denoting the visibility state of the document. Possible values are `visible`, `hidden`, `prerender`, and `unloaded`.

### Extensions for HTMLDocument

_The `Document` interface for HTML documents inherits from the [`HTMLDocument`](htmldocument) interface or, since HTML5, is extended for such documents._

[`Document.cookie`](document/cookie)  
Returns a semicolon-separated list of the cookies for that document or sets a single cookie.

[`Document.defaultView`](document/defaultview)<span class="badge inline readonly">Read only </span>  
Returns a reference to the window object.

[`Document.designMode`](document/designmode)  
Gets/sets the ability to edit the whole document.

[`Document.dir`](document/dir)  
Gets/sets directionality (rtl/ltr) of the document.

[`Document.domain`](document/domain) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Gets/sets the domain of the current document.

[`Document.lastModified`](document/lastmodified)<span class="badge inline readonly">Read only </span>  
Returns the date on which the document was last modified.

[`Document.location`](document/location)<span class="badge inline readonly">Read only </span>  
Returns the URI of the current document.

[`Document.readyState`](document/readystate)<span class="badge inline readonly">Read only </span>  
Returns loading status of the document.

[`Document.referrer`](document/referrer)<span class="badge inline readonly">Read only </span>  
Returns the URI of the page that linked to this page.

[`Document.title`](document/title)  
Sets or gets the title of the current document.

[`Document.URL`](document/url)<span class="badge inline readonly">Read only </span>  
Returns the document location as a string.

### Event handlers

[`Document.onafterscriptexecute`](document/onafterscriptexecute) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Represents the event handling code for the `afterscriptexecute` event.

[`Document.onbeforescriptexecute`](document/onbeforescriptexecute) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Represents the event handling code for the `beforescriptexecute` event.

<span class="page-not-created">`Document.oncopy`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Represents the event handling code for the `copy` event.

<span class="page-not-created">`Document.oncut`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Represents the event handling code for the `cut` event.

[`Document.onfullscreenchange`](document/onfullscreenchange)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `fullscreenchange` event is raised.

[`Document.onfullscreenerror`](document/onfullscreenerror)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `fullscreenerror` event is raised.

<span class="page-not-created">`Document.onpaste`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Represents the event handling code for the `paste` event.

<span class="page-not-created">`Document.onreadystatechange`</span>  
Represents the event handling code for the `readystatechange` event.

[`GlobalEventHandlers.onselectionchange`](globaleventhandlers/onselectionchange) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `selectionchange` event is raised.

[`Document.onvisibilitychange`](document/onvisibilitychange)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `visibilitychange` event is raised.

The `Document` interface is extended with the [`GlobalEventHandlers`](globaleventhandlers) interface:

[`GlobalEventHandlers.onabort`](globaleventhandlers/onabort)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the [`abort`](htmlmediaelement/abort_event) event is raised.

[`GlobalEventHandlers.onanimationcancel`](globaleventhandlers/onanimationcancel) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when an `animationcancel` event is sent, indicating that a running [CSS animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) has been canceled.

[`GlobalEventHandlers.onanimationend`](globaleventhandlers/onanimationend) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when an `animationend` event is sent, indicating that a [CSS animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) has stopped playing.

[`GlobalEventHandlers.onanimationiteration`](globaleventhandlers/onanimationiteration) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when an `animationiteration` event has been sent, indicating that a [CSS animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) has begun playing a new iteration of the animation sequence.

[`GlobalEventHandlers.onanimationstart`](globaleventhandlers/onanimationstart) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when an `animationstart` event is sent, indicating that a [CSS animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) has started playing.

[`GlobalEventHandlers.onauxclick`](globaleventhandlers/onauxclick) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when an `auxclick` event is sent, indicating that a non-primary button has been pressed on an input device (e.g. a middle mouse button).

[`GlobalEventHandlers.onblur`](globaleventhandlers/onblur)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `blur` event is raised.

[`GlobalEventHandlers.onerror`](globaleventhandlers/onerror)  
Is an <span class="page-not-created">`OnErrorEventHandler`</span> representing the code to be called when the `error` event is raised.

[`GlobalEventHandlers.onfocus`](globaleventhandlers/onfocus)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `focus` event is raised.

[`GlobalEventHandlers.oncancel`](globaleventhandlers/oncancel)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `cancel` event is raised.

[`GlobalEventHandlers.oncanplay`](globaleventhandlers/oncanplay)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `canplay` event is raised.

[`GlobalEventHandlers.oncanplaythrough`](globaleventhandlers/oncanplaythrough)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `canplaythrough` event is raised.

[`GlobalEventHandlers.onchange`](globaleventhandlers/onchange)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `change` event is raised.

[`GlobalEventHandlers.onclick`](globaleventhandlers/onclick)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `click` event is raised.

[`GlobalEventHandlers.onclose`](globaleventhandlers/onclose)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `close` event is raised.

[`GlobalEventHandlers.oncontextmenu`](globaleventhandlers/oncontextmenu)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `contextmenu` event is raised.

[`GlobalEventHandlers.oncuechange`](globaleventhandlers/oncuechange)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `cuechange` event is raised.

[`GlobalEventHandlers.ondblclick`](globaleventhandlers/ondblclick)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `dblclick` event is raised.

[`GlobalEventHandlers.ondrag`](globaleventhandlers/ondrag)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `drag` event is raised.

[`GlobalEventHandlers.ondragend`](globaleventhandlers/ondragend)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `dragend` event is raised.

[`GlobalEventHandlers.ondragenter`](globaleventhandlers/ondragenter)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `dragenter` event is raised.

[`GlobalEventHandlers.ondragexit`](globaleventhandlers/ondragleave) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `dragexit` event is raised.

[`GlobalEventHandlers.ondragleave`](globaleventhandlers/ondragleave)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `dragleave` event is raised.

[`GlobalEventHandlers.ondragover`](globaleventhandlers/ondragover)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `dragover` event is raised.

[`GlobalEventHandlers.ondragstart`](globaleventhandlers/ondragstart)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `dragstart` event is raised.

[`GlobalEventHandlers.ondrop`](globaleventhandlers/ondrop)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `drop` event is raised.

[`GlobalEventHandlers.ondurationchange`](globaleventhandlers/ondurationchange)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `durationchange` event is raised.

[`GlobalEventHandlers.onemptied`](globaleventhandlers/onemptied)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `emptied` event is raised.

[`GlobalEventHandlers.onended`](globaleventhandlers/onended)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `ended` event is raised.

[`GlobalEventHandlers.onformdata`](globaleventhandlers/onformdata)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `formdata` events, fired after the entry list representing the form's data is constructed.

[`GlobalEventHandlers.ongotpointercapture`](globaleventhandlers/ongotpointercapture)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `gotpointercapture` event type is raised.

[`GlobalEventHandlers.oninput`](globaleventhandlers/oninput)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `input` event is raised.

[`GlobalEventHandlers.oninvalid`](globaleventhandlers/oninvalid)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `invalid` event is raised.

[`GlobalEventHandlers.onkeydown`](globaleventhandlers/onkeydown)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `keydown` event is raised.

[`GlobalEventHandlers.onkeypress`](globaleventhandlers/onkeypress)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `keypress` event is raised.

[`GlobalEventHandlers.onkeyup`](globaleventhandlers/onkeyup)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `keyup` event is raised.

[`GlobalEventHandlers.onload`](globaleventhandlers/onload)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `load` event is raised.

[`GlobalEventHandlers.onloadeddata`](globaleventhandlers/onloadeddata)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `loadeddata` event is raised.

[`GlobalEventHandlers.onloadedmetadata`](globaleventhandlers/onloadedmetadata)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `loadedmetadata` event is raised.

[`GlobalEventHandlers.onloadend`](globaleventhandlers/onloadend)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `loadend` event is raised (when progress has stopped on the loading of a resource.)

[`GlobalEventHandlers.onloadstart`](globaleventhandlers/onloadstart)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `loadstart` event is raised (when progress has begun on the loading of a resource.)

[`GlobalEventHandlers.onlostpointercapture`](globaleventhandlers/onlostpointercapture)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `lostpointercapture` event type is raised.

[`GlobalEventHandlers.onmousedown`](globaleventhandlers/onmousedown)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `mousedown` event is raised.

[`GlobalEventHandlers.onmouseenter`](globaleventhandlers/onmouseenter)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `mouseenter` event is raised.

[`GlobalEventHandlers.onmouseleave`](globaleventhandlers/onmouseleave)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `mouseleave` event is raised.

[`GlobalEventHandlers.onmousemove`](globaleventhandlers/onmousemove)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `mousemove` event is raised.

[`GlobalEventHandlers.onmouseout`](globaleventhandlers/onmouseout)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `mouseout` event is raised.

[`GlobalEventHandlers.onmouseover`](globaleventhandlers/onmouseover)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `mouseover` event is raised.

[`GlobalEventHandlers.onmouseup`](globaleventhandlers/onmouseup)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `mouseup` event is raised.

[`GlobalEventHandlers.onmousewheel`](globaleventhandlers/onmousewheel) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `mousewheel` event is raised. Deprecated. Use `onwheel` instead.

[`GlobalEventHandlers.onwheel`](globaleventhandlers/onwheel)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `wheel` event is raised.

[`GlobalEventHandlers.onpause`](globaleventhandlers/onpause)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `pause` event is raised.

[`GlobalEventHandlers.onplay`](globaleventhandlers/onplay)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `play` event is raised.

[`GlobalEventHandlers.onplaying`](globaleventhandlers/onplaying)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `playing` event is raised.

[`GlobalEventHandlers.onpointerdown`](globaleventhandlers/onpointerdown)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `pointerdown` event is raised.

[`GlobalEventHandlers.onpointermove`](globaleventhandlers/onpointermove)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `pointermove` event is raised.

[`GlobalEventHandlers.onpointerup`](globaleventhandlers/onpointerup)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `pointerup` event is raised.

[`GlobalEventHandlers.onpointercancel`](globaleventhandlers/onpointercancel)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `pointercancel` event is raised.

[`GlobalEventHandlers.onpointerover`](globaleventhandlers/onpointerover)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `pointerover` event is raised.

[`GlobalEventHandlers.onpointerout`](globaleventhandlers/onpointerout)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `pointerout` event is raised.

[`GlobalEventHandlers.onpointerenter`](globaleventhandlers/onpointerenter)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `pointerenter` event is raised.

[`GlobalEventHandlers.onpointerleave`](globaleventhandlers/onpointerleave)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `pointerleave` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onpointerlockchange`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `pointerlockchange` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onpointerlockerror`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `pointerlockerror` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onprogress`</span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `progress` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onratechange`</span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `ratechange` event is raised.

[`GlobalEventHandlers.onreset`](globaleventhandlers/onreset)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `reset` event is raised.

[`GlobalEventHandlers.onresize`](globaleventhandlers/onresize)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `resize` event is raised.

[`GlobalEventHandlers.onscroll`](globaleventhandlers/onscroll)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `scroll` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onseeked`</span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `seeked` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onseeking`</span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `seeking` event is raised.

[`GlobalEventHandlers.onselect`](globaleventhandlers/onselect)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `select` event is raised.

[`GlobalEventHandlers.onselectstart`](globaleventhandlers/onselectstart)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `selectionchange` event is raised, i.e. when the user starts to make a new text selection on a web page.

[`GlobalEventHandlers.onselectionchange`](globaleventhandlers/onselectionchange)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `selectionchange` event is raised, i.e. when the text selected on a web page changes.

<span class="page-not-created">`GlobalEventHandlers.onshow`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `show` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onsort`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `sort` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onstalled`</span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `stalled` event is raised.

[`GlobalEventHandlers.onsubmit`](globaleventhandlers/onsubmit)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `submit` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onsuspend`</span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `suspend` event is raised.

<span class="page-not-created">`GlobalEventHandlers.ontimeupdate`</span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `timeupdate` event is raised.

<span class="page-not-created">`GlobalEventHandlers.onvolumechange`</span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `volumechange` event is raised.

[`GlobalEventHandlers.ontouchcancel`](globaleventhandlers/ontouchcancel) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `touchcancel` event is raised.

[`GlobalEventHandlers.ontouchend`](globaleventhandlers/ontouchend) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `touchend` event is raised.

[`GlobalEventHandlers.ontouchmove`](globaleventhandlers/ontouchmove) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `touchmove` event is raised.

[`GlobalEventHandlers.ontouchstart`](globaleventhandlers/ontouchstart) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `touchstart` event is raised.

[`GlobalEventHandlers.ontransitioncancel`](globaleventhandlers/ontransitioncancel)  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when a `transitioncancel` event is sent, indicating that a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions) has been cancelled.

[`GlobalEventHandlers.ontransitionend`](globaleventhandlers/ontransitionend)  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when a `transitionend` event is sent, indicating that a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions) has finished playing.

<span class="page-not-created">`GlobalEventHandlers.ontransitionrun`</span>  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when a `transitionrun` event is sent, indicating that a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions) is running, though not nessarilty started.

<span class="page-not-created">`GlobalEventHandlers.ontransitionstart`</span>  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when a `transitionstart` event is sent, indicating that a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions) has started transitioning.

<span class="page-not-created">`GlobalEventHandlers.onwaiting`</span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `waiting` event is raised.

### Deprecated properties

[`Document.alinkColor`](document/alinkcolor) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns or sets the color of active links in the document body.

[`Document.all`](document/all) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Provides access to all elements in the document — it returns an <span class="page-not-created">`HTMLAllCollection`</span> rooted at the document node. This is a legacy, non-standard property and should not be used.

[`Document.anchors`](document/anchors) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>  
Returns a list of all of the anchors in the document.

[`Document.applets`](document/applets) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>  
Returns an ordered list of the applets within a document.

[`Document.bgColor`](document/bgcolor) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Gets/sets the background color of the current document.

[`Document.charset`](document/characterset) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>  
Alias of [`Document.characterSet`](document/characterset). Use this property instead.

[`Document.domConfig`](document) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Should return a <span class="page-not-created">`DOMConfiguration`</span> object.

[`Document.fgColor`](document/fgcolor) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Gets/sets the foreground color, or text color, of the current document.

[`Document.fullscreen`](document/fullscreen) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
`true` when the document is in <span class="page-not-created">`full-screen mode`</span>.

[`Document.height`](document/height) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Gets/sets the height of the current document.

[`Document.inputEncoding`](document/characterset) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>  
Alias of [`Document.characterSet`](document/characterset). Use this property instead.

[`Document.lastStyleSheetSet`](document/laststylesheetset) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>  
Returns the name of the style sheet set that was last enabled. Has the value `null` until the style sheet is changed by setting the value of [`selectedStyleSheetSet`](document/selectedstylesheetset).

[`Document.linkColor`](document/linkcolor) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Gets/sets the color of hyperlinks in the document.

[`Document.preferredStyleSheetSet`](document/preferredstylesheetset) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>  
Returns the preferred style sheet set as specified by the page author.

[`Document.rootElement`](document/rootelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Like [`Document.documentElement`](document/documentelement), but only for [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) root elements. Use this property instead.

[`Document.selectedStyleSheetSet`](document/selectedstylesheetset) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns which style sheet set is currently in use.

[`Document.styleSheetSets`](document/stylesheetsets) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>  
Returns a list of the style sheet sets available on the document.

[`Document.vlinkColor`](document/vlinkcolor) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Gets/sets the color of visited hyperlinks.

[`Document.width`](document/width) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns the width of the current document.

[`Document.xmlEncoding`](document/xmlencoding) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns the encoding as determined by the XML declaration.

<span class="page-not-created">`Document.xmlStandalone`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns `true` if the XML declaration specifies the document to be standalone (_e.g.,_ An external part of the DTD affects the document's content), else `false`.

[`Document.xmlVersion`](document/xmlversion) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns the version number as specified in the XML declaration or `"1.0"` if the declaration is absent.

## Methods

_This interface also inherits from the [`Node`](node) and [`EventTarget`](eventtarget) interfaces._

[`Document.adoptNode()`](document/adoptnode)  
Adopt node from an external document.

[`Document.append()`](document/append)  
Inserts a set of [`Node`](node) objects or [`DOMString`](domstring) objects after the last child of the document.

<span class="page-not-created">`Document.captureEvents()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
See [`Window.captureEvents`](window/captureevents).

[`Document.caretPositionFromPoint()`](document/caretpositionfrompoint)  
Returns a [`CaretPosition`](caretposition) object containing the DOM node containing the caret, and caret's character offset within that node.

[`Document.caretRangeFromPoint()`](document/caretrangefrompoint) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Gets a [`Range`](range) object for the document fragment under the specified coordinates.

[`Document.createAttribute()`](document/createattribute)  
Creates a new [`Attr`](attr) object and returns it.

<span class="page-not-created">`Document.createAttributeNS()`</span>  
Creates a new attribute node in a given namespace and returns it.

[`Document.createCDATASection()`](document/createcdatasection)  
Creates a new CDATA node and returns it.

[`Document.createComment()`](document/createcomment)  
Creates a new comment node and returns it.

[`Document.createDocumentFragment()`](document/createdocumentfragment)  
Creates a new document fragment.

[`Document.createElement()`](document/createelement)  
Creates a new element with the given tag name.

[`Document.createElementNS()`](document/createelementns)  
Creates a new element with the given tag name and namespace URI.

[`Document.createEntityReference()`](document/createentityreference) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Creates a new entity reference object and returns it.

[`Document.createEvent()`](document/createevent)  
Creates an event object.

[`Document.createNodeIterator()`](document/createnodeiterator)  
Creates a [`NodeIterator`](nodeiterator) object.

[`Document.createProcessingInstruction()`](document/createprocessinginstruction)  
Creates a new [`ProcessingInstruction`](processinginstruction) object.

[`Document.createRange()`](document/createrange)  
Creates a [`Range`](range) object.

[`Document.createTextNode()`](document/createtextnode)  
Creates a text node.

[`Document.createTouch()`](document/createtouch) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Creates a [`Touch`](touch) object.

[`Document.createTouchList()`](document/createtouchlist) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Creates a [`TouchList`](touchlist) object.

[`Document.createTreeWalker()`](document/createtreewalker)  
Creates a [`TreeWalker`](treewalker) object.

[`Document.elementFromPoint()`](document/elementfrompoint)  
Returns the topmost element at the specified coordinates.

[`Document.elementsFromPoint()`](document/elementsfrompoint)  
Returns an array of all elements at the specified coordinates.

[`Document.enableStyleSheetsForSet()`](document/enablestylesheetsforset) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Enables the style sheets for the specified style sheet set.

[`Document.exitPictureInPicture()`](document/exitpictureinpicture)  
Remove the video from the floating picture-in-picture window back to its original container.

[`Document.exitPointerLock()`](document/exitpointerlock) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Release the pointer lock.

[`Document.getAnimations()`](document/getanimations)  
Returns an array of all [`Animation`](animation) objects currently in effect, whose target elements are descendants of the `document`.

[`Document.getElementsByClassName()`](document/getelementsbyclassname)  
Returns a list of elements with the given class name.

[`Document.getElementsByTagName()`](document/getelementsbytagname)  
Returns a list of elements with the given tag name.

[`Document.getElementsByTagNameNS()`](document/getelementsbytagnamens)  
Returns a list of elements with the given tag name and namespace.

[`Document.getSelection()`](document/getselection)  
Returns a [`Selection`](selection) object representing the range of text selected by the user, or the current position of the caret.

[`Document.hasStorageAccess()`](document/hasstorageaccess) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a boolean value indicating whether the document has access to its first-party storage.

[`Document.importNode()`](document/importnode)  
Returns a clone of a node from an external document.

<span class="page-not-created">`Document.normalizeDocument()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Replaces entities, normalizes text nodes, etc.

[`Document.prepend()`](document/prepend)  
Inserts a set of [`Node`](node) objects or [`DOMString`](domstring) objects before the first child of the document.

[`Document.releaseCapture()`](document/releasecapture) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Releases the current mouse capture if it's on an element in this document.

<span class="page-not-created">`Document.releaseEvents()`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
See [`Window.releaseEvents()`](window/releaseevents).

[`Document.replaceChildren()`](document/replacechildren)  
Replaces the existing children of a document with a specified new set of children.

[`Document.requestStorageAccess()`](document/requeststorageaccess)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves if the access to first-party storage was granted, and rejects if access was denied.

<span class="page-not-created">`Document.routeEvent()`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
See [`Window.routeEvent()`](window/routeevent).

[`Document.mozSetImageElement()`](document/mozsetimageelement) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Allows you to change the element being used as the background image for a specified element ID.

The `Document` interface is extended with the [`ParentNode`](parentnode) interface:

[`document.getElementById(String id)`](document/getelementbyid)  
Returns an object reference to the identified element.

[`Document.querySelector()`](document/queryselector)  
Returns the first Element node within the document, in document order, that matches the specified selectors.

[`Document.querySelectorAll()`](document/queryselectorall)  
Returns a list of all the Element nodes within the document that match the specified selectors.

The `Document` interface is extended with the [`XPathEvaluator`](xpathevaluator) interface:

[`Document.createExpression()`](document/createexpression)  
Compiles an `XPathExpression` which can then be used for (repeated) evaluations.

[`Document.createNSResolver()`](document/creatensresolver)  
Creates an [`XPathNSResolver`](xpathnsresolver) object.

[`Document.evaluate()`](document/evaluate)  
Evaluates an XPath expression.

### Extension for HTML documents

The `Document` interface for HTML documents inherit from the [`HTMLDocument`](htmldocument) interface or, since HTML5, is extended for such documents:

[`Document.clear()`](document/clear) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
In majority of modern browsers, including recent versions of Firefox and Internet Explorer, this method does nothing.

[`Document.close()`](document/close)  
Closes a document stream for writing.

[`Document.execCommand()`](document/execcommand) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
On an editable document, executes a formatting command.

[`Document.getElementsByName()`](document/getelementsbyname)  
Returns a list of elements with the given name.

[`Document.hasFocus()`](document/hasfocus)  
Returns `true` if the focus is currently located anywhere inside the specified document.

[`Document.open()`](document/open)  
Opens a document stream for writing.

[`Document.queryCommandEnabled()`](document/querycommandenabled) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns true if the formatting command can be executed on the current range.

<span class="page-not-created">`Document.queryCommandIndeterm()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns true if the formatting command is in an indeterminate state on the current range.

[`Document.queryCommandState()`](document/querycommandstate) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns true if the formatting command has been executed on the current range.

[`Document.queryCommandSupported()`](document/querycommandsupported) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns true if the formatting command is supported on the current range.

<span class="page-not-created">`Document.queryCommandValue()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns the current value of the current range for a formatting command.

[`Document.write()`](document/write)  
Writes text in a document.

[`Document.writeln()`](document/writeln)  
Writes a line of text in a document.

## Events

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

[`scroll`](document/scroll_event)  
Fired when the document view or an element has been scrolled.  
Also available via the [`onscroll`](globaleventhandlers/onscroll) property.

[`visibilitychange`](document/visibilitychange_event)  
Fired when the content of a tab has become visible or has been hidden.  
Also available via the [`onvisibilitychange`](document/onvisibilitychange) property.

[`wheel`](document/wheel_event)  
Fired when the user rotates a wheel button on a pointing device (typically a mouse).  
Also available via the [`onwheel`](globaleventhandlers/onwheel) property.

### Animation events

[`animationcancel`](document/animationcancel_event)  
Fired when an animation unexpectedly aborts.  
Also available via the [`onanimationcancel`](globaleventhandlers/onanimationcancel) property.

[`animationend`](document/animationend_event)  
Fired when an animation has completed normally.  
Also available via the [`onanimationend`](globaleventhandlers/onanimationend) property.

[`animationiteration`](document/animationiteration_event)  
Fired when an animation iteration has completed.  
Also available via the [`onanimationiteration`](globaleventhandlers/onanimationiteration) property.

[`animationstart`](document/animationstart_event)  
Fired when an animation starts.  
Also available via the [`onanimationstart`](globaleventhandlers/onanimationstart) property.

### Clipboard events

[`copy`](document/copy_event)  
Fired when the user initiates a copy action through the browser's user interface.  
Also available via the [`oncopy`](htmlelement/oncopy) property.

[`cut`](document/cut_event)  
Fired when the user initiates a cut action through the browser's user interface.  
Also available via the [`oncut`](htmlelement/oncut) property.

[`paste`](document/paste_event)  
Fired when the user initiates a paste action through the browser's user interface.  
Also available via the [`onpaste`](htmlelement/onpaste) property.

### Drag & drop events

[`drag`](document/drag_event)  
Fired every few hundred milliseconds as an element or text selection is being dragged by the user.  
Also available via the [`ondrag`](globaleventhandlers/ondrag) property.

[`dragend`](document/dragend_event)  
Fired when a drag operation is being ended (by releasing a mouse button or hitting the escape key).  
Also available via the [`ondragend`](globaleventhandlers/ondragend) property.

[`dragenter`](document/dragenter_event)  
Fired when a dragged element or text selection enters a valid drop target.  
Also available via the [`ondragenter`](globaleventhandlers/ondragenter) property.

[`dragleave`](document/dragleave_event)  
Fired when a dragged element or text selection leaves a valid drop target.  
Also available via the [`ondragleave`](globaleventhandlers/ondragleave) property.

[`dragover`](document/dragover_event)  
Fired when an element or text selection is being dragged over a valid drop target (every few hundred milliseconds).  
Also available via the [`ondragover`](globaleventhandlers/ondragover) property.

[`dragstart`](document/dragstart_event)  
Fired when the user starts dragging an element or text selection.  
Also available via the [`ondragstart`](globaleventhandlers/ondragstart) property.

[`drop`](document/drop_event)  
Fired when an element or text selection is dropped on a valid drop target.  
Also available via the [`ondrop`](globaleventhandlers/ondrop) property.

### Fullscreen events

[`fullscreenchange`](document/fullscreenchange_event)  
Fired when the `Document` transitions into or out of [full-screen](fullscreen_api/guide) mode.  
Also available via the [`onfullscreenchange`](document/onfullscreenchange) property.

`fullscreenerror`  
Fired if an error occurs while attempting to switch into or out of [full-screen](fullscreen_api/guide) mode.  
Also available via the [`onfullscreenerror`](document/onfullscreenerror) property.

### Keyboard events

[`keydown`](document/keydown_event)  
Fired when a key is pressed.  
Also available via the [`onkeydown`](globaleventhandlers/onkeydown) property.

[`keypress`](document/keypress_event)  
Fired when a key that produces a character value is pressed down. <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Also available via the [`onkeypress`](globaleventhandlers/onkeypress) property.

[`keyup`](document/keyup_event)  
Fired when a key is released.  
Also available via the [`onkeyup`](globaleventhandlers/onkeyup) property.

### Load & unload events

[`DOMContentLoaded`](document/domcontentloaded_event)  
Fired when the document has been completely loaded and parsed, without waiting for stylesheets, images, and subframes to finish loading.

[`readystatechange`](document/readystatechange_event)  
Fired when the [`readyState`](document/readystate) attribute of a document has changed.  
Also available via the `onreadystatechange` property.

### Pointer events

[`gotpointercapture`](document/gotpointercapture_event)  
Fired when an element captures a pointer using `setPointerCapture()`.  
Also available via the [`ongotpointercapture`](globaleventhandlers/ongotpointercapture) property.

[`lostpointercapture`](document/lostpointercapture_event)  
Fired when a [captured pointer](pointer_events#pointer_capture) is released.  
Also available via the [`onlostpointercapture`](globaleventhandlers/onlostpointercapture) property.

[`pointercancel`](document/pointercancel_event)  
Fired when a pointer event is canceled.  
Also available via the [`onpointercancel`](globaleventhandlers/onpointercancel) property.

[`pointerdown`](document/pointerdown_event)  
Fired when a pointer becomes active.  
Also available via the [`onpointerdown`](globaleventhandlers/onpointerdown) property.

[`pointerenter`](document/pointerenter_event)  
Fired when a pointer is moved into the hit test boundaries of an element or one of its descendants.  
Also available via the [`onpointerenter`](globaleventhandlers/onpointerenter) property.

[`pointerleave`](document/pointerleave_event)  
Fired when a pointer is moved out of the hit test boundaries of an element.  
Also available via the [`onpointerleave`](globaleventhandlers/onpointerleave) property.

[`pointerlockchange`](document/pointerlockchange_event)  
Fired when the pointer is locked/unlocked.  
Also available via the <span class="page-not-created">`onpointerlockchange`</span> property.

[`pointerlockerror`](document/pointerlockerror_event)  
Fired when locking the pointer failed.  
Also available via the <span class="page-not-created">`onpointerlockerror`</span> property.

[`pointermove`](document/pointermove_event)  
Fired when a pointer changes coordinates.  
Also available via the [`onpointermove`](globaleventhandlers/onpointermove) property.

[`pointerout`](document/pointerout_event)  
Fired when a pointer is moved out of the _hit test_ boundaries of an element (among other reasons).  
Also available via the [`onpointerout`](globaleventhandlers/onpointerout) property.

[`pointerover`](document/pointerover_event)  
Fired when a pointer is moved into an element's hit test boundaries.  
Also available via the [`onpointerover`](globaleventhandlers/onpointerover) property.

[`pointerup`](document/pointerup_event)  
Fired when a pointer is no longer active.  
Also available via the [`onpointerup`](globaleventhandlers/onpointerup) property.

### Selection events

[`selectionchange`](document/selectionchange_event)  
Fired when the current text selection on a document is changed.  
Also available via the [`onselectionchange`](globaleventhandlers/onselectionchange) property.

[`selectstart`](document/selectstart_event)  
Fired when the user begins a new selection.  
Also available via the [`onselectstart`](globaleventhandlers/onselectstart) property.

### Touch events

[`touchcancel`](document/touchcancel_event)  
Fired when one or more touch points have been disrupted in an implementation-specific manner (for example, too many touch points are created).  
Also available via the [`ontouchcancel`](globaleventhandlers/ontouchcancel) property.

[`touchend`](document/touchend_event)  
Fired when one or more touch points are removed from the touch surface.  
Also available via the [`ontouchend`](globaleventhandlers/ontouchend) property

[`touchmove`](document/touchmove_event)  
Fired when one or more touch points are moved along the touch surface.  
Also available via the [`ontouchmove`](globaleventhandlers/ontouchmove) property

[`touchstart`](document/touchstart_event)  
Fired when one or more touch points are placed on the touch surface.  
Also available via the [`ontouchstart`](globaleventhandlers/ontouchstart) property

### Transition events

[`transitioncancel`](document/transitioncancel_event)  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) is canceled.  
Also available via the [`ontransitioncancel`](globaleventhandlers/ontransitioncancel) property.

[`transitionend`](document/transitionend_event)  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) has completed.  
Also available via the [`ontransitionend`](globaleventhandlers/ontransitionend) property.

[`transitionrun`](document/transitionrun_event)  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) is first created.  
Also available via the <span class="page-not-created">`ontransitionrun`</span> property.

[`transitionstart`](document/transitionstart_event)  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) has actually started.  
Also available via the <span class="page-not-created">`ontransitionstart`</span> property.

## Non-standard extensions <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

### Firefox notes

Mozilla defines a set of non-standard properties made only for XUL content:

[`Document.currentScript`](document/currentscript) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Returns the [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) element that is currently executing.

[`Document.documentURIObject`](document/documenturiobject)  
(**Mozilla add-ons only!**) Returns the <span class="page-not-created">`nsIURI`</span> object representing the URI of the document. This property only has special meaning in privileged JavaScript code (with UniversalXPConnect privileges).

[`Document.popupNode`](document/popupnode)  
Returns the node upon which a popup was invoked.

[`Document.tooltipNode`](document/tooltipnode)  
Returns the node which is the target of the current tooltip.

Mozilla also define some non-standard methods:

<span class="page-not-created">`Document.execCommandShowHelp()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
This method never did anything and always threw an exception, so it was removed in Gecko 14.0 (Firefox 14.0 / Thunderbird 14.0 / SeaMonkey 2.11).

[`Document.getBoxObjectFor()`](document/getboxobjectfor) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Use the [`Element.getBoundingClientRect()`](element/getboundingclientrect) method instead.

<span class="page-not-created">`Document.loadOverlay()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Loads a [XUL overlay](https://developer.mozilla.org/en-US/docs/XUL_Overlays) dynamically. This only works in XUL documents.

<span class="page-not-created">`Document.queryCommandText()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
This method never did anything but throw an exception, and was removed in Gecko 14 (Firefox 14 / Thunderbird 14 / SeaMonkey 2.11).

### Internet Explorer notes

Microsoft defines some non-standard properties:

<span class="page-not-created">`Document.fileSize`</span>\* <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns size in bytes of the document. Starting with Internet Explorer 11, that property is no longer supported. See [MSDN](https://msdn.microsoft.com/en-us/library/ms533752%28v=VS.85%29.aspx).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-document">DOM<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Intend to supersede DOM 3</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/dom.html#the-document-object">HTML Living Standard<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Turn the <a href="htmldocument"><code>HTMLDocument</code></a> interface into a <code>Document</code> extension.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#extensions-to-the-document-interface">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Extend the <code>Document</code> interface</td></tr><tr class="even"><td><a href="https://w3c.github.io/pointerlock/#extensions-to-the-document-interface">Pointer Lock<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Extend the <code>Document</code> interface</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/page-visibility/#extensions-to-the-document-interface">Page Visibility (Second Edition)<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Extend the <code>Document</code> interface with the <code>visibilityState</code> and <code>hidden</code> attributes and the <code>onvisibilitychange</code> event listener.</td></tr><tr class="even"><td><a href="https://w3c.github.io/selection-api/#extensions-to-document-interface">Selection API<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds <code>getSelection()</code>, <code>onselectstart</code> and <code>onselectionchange</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/dom/#interface-document">DOM4<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Supersede DOM 3</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/#i-Document">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Supersede DOM 2</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-XPath/xpath.html#XPathEvaluator">Document Object Model (DOM) Level 3 XPath Specification<br />
<span class="small">The definition of 'XPathEvaluator' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Define the <a href="xpathevaluator"><code>XPathEvaluator</code></a> interface which extend document.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/#i-Document">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Supersede DOM 1</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/#i-Document">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition for the interface</td></tr></tbody></table>

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

`Document`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

`Document`

60

17

20

No

47

6.1

60

60

20

44

6.1

8.0

`DOMContentLoaded_event`

1

12

1

9

9

3.1

1

18

4

10.1

2

1.0

`URL`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

`adoptNode`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`alinkColor`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

1

4

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1.2-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

4

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

`all`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

24

4

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

3-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

≤37-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

24

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

`anchors`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`animationcancel_event`

No

No

54

No

No

13.1

12

No

No

54

No

13.4

12

No

`animationend_event`

43

12

Yes

10

30

9

43

43

Yes

30

9

4.0

`animationiteration_event`

43

12

51

10

30

9

43

43

51

30

9

4.0

`animationstart_event`

43

12

51

10

30

9

43

43

51

30

9

4.0

`applets`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`bgColor`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

1

4

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

4

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

`body`

1

12

1

The `body` property was implemented on the `HTMLDocument` interface in Firefox for a long time, hence `document.body` would not return the `<body>` element if the document's `Content-Type` was not set to `text/html` or `application/xhtml+xml` (or if it came from `DOMParser.parseFromString` without the `text/html` type being used). This has been fixed in Firefox 60.

4

9.6

1

1

18

4

The `body` property was implemented on the `HTMLDocument` interface in Firefox for a long time, hence `document.body` would not return the `<body>` element if the document's `Content-Type` was not set to `text/html` or `application/xhtml+xml` (or if it came from `DOMParser.parseFromString` without the `text/html` type being used). This has been fixed in Firefox 60.

10.1

1

1.0

`captureEvents`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

1

11

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

4

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

`caretPositionFromPoint`

No

No

20

No

No

No

No

No

20

No

No

No

`caretRangeFromPoint`

4

12

No

No

15

5

≤37

18

No

14

4

1.0

`characterSet`

1

1

`charset` alias was made read-only in Chrome 45.

1

12

12

12

1

44

1.5

9

4

9

≤12.1

No

No

3

3

3

1

1

`charset` alias was made read-only in WebView 45.

1

18

18

`charset` alias was made read-only in Chrome 45.

18

4

44

4

Yes

No

No

1

1

1

1.0

1.0

`charset` alias was made read-only in Samsung Internet 5.0.

1.0

`clear`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

1

4

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

1

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

4

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

1

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

`close`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

1

4

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

4

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

`compatMode`

1

12

1

6

≤12.1

3.1

1

18

4

≤12.1

2

1.0

`contentType`

36

17

1

No

23

≤12.1-15

9

37

36

4

24

≤12.1-14

9

3.0

`cookie`

1

12

1

Prior to Firefox 68, `cookie` was available only on HTML documents; it is now available on all documents, such as XML and SVG.

4

3

1

1

18

4

Prior to Firefox 68, `cookie` was available only on HTML documents; it is now available on all documents, such as XML and SVG.

10.1

1

1.0

`copy_event`

1

≤18

Yes

No

15

Yes

1

18

Yes

14

?

1.0

`createAttribute`

1

12

44

1-44

The parameter was not converted to its lowercase variant.

6

≤12.1

1

1

18

44

4-44

The parameter was not converted to its lowercase variant.

≤12.1

1

1.0

`createAttributeNS`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`createCDATASection`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`createComment`

1

12

1

6

≤12.1

1

1

18

4

≤12.1

1

1.0

`createDocumentFragment`

1

12

1

6

≤12.1

1

1

18

4

≤12.1

1

1.0

`createElement`

1

12

1

Doesn't conform to the DOM spec for XUL and XHTML documents: `localName` and `namespaceURI` are not set to null on the created element.

5

6

1

1

18

4

10.1

1

1.0

`createElementNS`

1

12

1

Doesn't conform to the DOM spec for XUL and XHTML documents: `localName` and `namespaceURI` are not set to null on the created element.

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`createEntityReference`

1-29

No

1-7

No

15-16

1-10

1-≤37

18-29

4-7

14-16

1-10

1.0-2.0

`createEvent`

1

12

1

From version 67, creating touch events using this method is no longer supported.

9

7

1

1

18

4

10.1

1

1.0

`createExpression`

1

12

1

No

≤12.1

3

1

18

4

≤12.1

1

1.0

`createNodeIterator`

1

12

1

9

9

3

1

18

4

Yes

1

1.0

`createNSResolver`

1

12

1

No

≤12.1

3

1

18

4

≤12.1

1

1.0

`createProcessingInstruction`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`createRange`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`createTextNode`

1

12

1

5

7

1

1

18

4

10.1

1

1.0

`createTouch`

No

No

18-67

No

No

No

≤37-68

Since WebView 55, all parameters are optional.

25-68

Since Chrome 55, all parameters are optional.

6

14-48

Since Opera Android 42, all parameters are optional.

≤3

1.5-10.0

Since Samsung Internet 6.0, all parameters are optional.

`createTouchList`

22-69

No

18-67

No

Yes-56

No

≤37-69

25-69

6

Yes-48

≤3

1.5-10.0

`createTreeWalker`

1

12

1

9

9

3

1

18

4

10.1

3

1.0

`currentScript`

29

12

4

No

16

6.1

≤37

29

4

16

8

2.0

`cut_event`

1

≤18

Yes

No

15

Yes

1

18

Yes

14

?

1.0

`defaultView`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`designMode`

1

12

1

4

9

1.2

1

18

4

10.1

1

1.0

`dir`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

1

Incorrect behavior before Firefox 23.

5

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

10.1

1-10.1

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

4

Incorrect behavior before Firefox 23.

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

10.3

1-10.3

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

`doctype`

1

12

1

6

≤12.1

1

1

18

4

≤12.1

1

1.0

`documentElement`

1

12

1

5

7

1

1

18

4

10.1

1

1.0

`documentURI`

1

17

1

No

≤12.1

3

1

18

4

≤12.1

1

1.0

`documentURIObject`

No

No

Yes-57

Available only to [legacy extensions](https://developer.mozilla.org/docs/Archive/Add-ons).

No

No

No

No

No

Yes-57

Available only to [legacy extensions](https://developer.mozilla.org/docs/Archive/Add-ons).

No

No

No

`domain`

1

12

1

From Firefox 62, if the domain cannot be identified, `domain` returns an empty string instead of `null`. See [bug 819475](https://bugzil.la/819475).

4

≤12.1

1

1

18

4

From Firefox 62, if the domain cannot be identified, `domain` returns an empty string instead of `null`. See [bug 819475](https://bugzil.la/819475).

≤12.1

1

1.0

`drag_event`

4

12

3.5

Firefox doesn't set the mouse coordinates during the drag event. See [bug 505521](https://bugzil.la/505521).

10

12

3.1

No

No

No

No

11

No

`dragend_event`

4

Prior to Chrome 72, the `dragend` event was not dispatched if an iframe (not necessarily the source target) is involved in a DOM operation. See [issue 737691](https://crbug.com/737691) for more details.

12

3.5

\["Firefox doesn't set the mouse coordinates during the drag event. See [bug 505521](https://bugzil.la/505521).", "In Firefox, `dragend` is not dispatched if the source node is moved or removed during the drag (e.g. on `drop` or `dragover`). See [bug 460801](https://bugzil.la/460801) for details."\]

10

12

3.1

No

No

No

No

11

No

`dragenter_event`

4

12

3.5

In Firefox, the `dragenter` event is fired twice when the dropzone is parent of draggable or draggable itself. See [bug 804036](https://bugzil.la/804036) for details.

10

12

3.1

No

No

No

No

11

No

`dragexit_event`

No

12-79

3.5

10

12

3.1

No

No

No

No

No

No

`dragleave_event`

4

12

3.5

10

12

3.1

No

No

No

No

11

No

`dragover_event`

4

12

3.5

10

12

3.1

No

No

No

No

11

No

`dragstart_event`

4

12

3.5

10

12

3.1

No

No

No

No

11

No

`drop_event`

4

12

3.5

10

12

3.1

No

No

No

No

11

No

`embeds`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

1

4

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

10.1

2-10.1

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

4

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

10.3

1-10.3

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

`enableStyleSheetsForSet`

No

No

3

No

No

No

No

No

4

No

No

No

`evaluate`

1

12

1

No

9

3

1

18

4

10.1

1

1.0

`execCommand`

1

12

1

From Firefox 82, nested calls are not supported (return `false`). See [bug 1634262](https://bugzil.la/1634262).

4

9

1.3

1

18

4

From Firefox 82, nested calls are not supported (return `false`). See [bug 1634262](https://bugzil.la/1634262).

10.1

1

1.0

`execCommandShowHelp`

No

12-79

1-14

This method never did anything and always threw an exception.

4

No

No

No

No

4-14

This method never did anything and always threw an exception.

No

No

No

`exitFullscreen`

71

15

12

64

9

11

15

5.1

71

≤37

71

18

64

9

Yes

No

10.0

1.0

`exitPictureInPicture`

69

79

No

No

56

13.1

No

No

No

No

13.4

No

`exitPointerLock`

37

22

13

50

Yes

No

24

15

10.1

37

≤37

37

25

50

Yes

24

14

10.3

3.0

1.5

`featurePolicy`

74

73-74

69-73

79

69

65-69

No

62

60-62

56-60

No

74

74

73-74

69-73

65

48

No

11.0

`fgColor`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

1

4

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

4

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

`fileSize`

No

No

No

5.5-11

No

No

No

No

No

No

No

No

`fonts`

35

79

41

No

22

10

≤37

35

41

22

10

3.0

`forms`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`fragmentDirective`

86

86

No

No

72

No

86

86

No

61

No

14.0

`fullscreen`

71

15

79

≤79

64

9

No

58

15

6

71

≤37

71

18

64

9

50

14

6

10.0

1.0

`fullscreenchange_event`

71

45

12

64

10

11

32

?

71

45

71

45

64

10

32

?

5.0

`fullscreenEnabled`

71

Yes

12

64

10

11

Yes

6

71

Yes

71

Yes

64

10

Yes

6

10.0

Yes

`fullscreenerror_event`

71

45

12

64

10

11

32

?

71

45

71

45

64

10

32

?

5.0

`getBoxObjectFor`

No

No

1-3.6

No

No

No

No

No

No

No

No

No

`getElementById`

1

12

1

5.5

7

1

1

18

4

10.1

1

1.0

`getElementsByClassName`

1

12

3

9

9.5

3.1

1

18

4

10.1

2

1.0

`getElementsByName`

1

12

Before Edge 79, this method returns an `HTMLCollection`, not a `NodeList`.

1

5

Returns an `HTMLCollection`, not a `NodeList`

5

1

1

18

4

10.1

1

1.0

`getElementsByTagName`

1

12

1

5

5.1

1

1

18

4

10.1

1

1.0

`getElementsByTagNameNS`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`getSelection`

1

12

1

9

≤12.1

4

1

18

4

≤12.1

3.2

1.0

`gotpointercapture_event`

57

≤79

59

?

44

13

57

57

79

43

13

7.0

`hasFocus`

1

12

3

5.5

15

4

1

18

4

14

3.2

1.0

`hasStorageAccess`

78

85

65

No

65

11.1

No

78

65

No

11.3

No

`head`

4

12

4

9

11

5

≤37

Yes

4

Yes

4

Yes

`height`

1-31

No

1-6

No

15-18

1-10

1-4.4.3

18-31

4-6

14-18

1-10

1.0-3.0

`hidden`

33

13

12

18

Since Firefox 56 it also returns `true` on Mac when the window is completely hidden by another non-translucent application.

10-52

10

12.1

6.1

4.4.3

≤37

33

Yes

18

Since Firefox 56 it also returns `true` on Mac when the window is completely hidden by another non-translucent application.

10-52

12.1

7

2.0

1.0

`images`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`implementation`

1

12

1

6

≤12.1

1

1

18

4

≤12.1

1

1.0

`importNode`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`keydown_event`

1

12

14

9

11.6

2

1

18

14

12

1

1.0

`keypress_event`

1

Chrome does not fire the `keypress` event for [known keyboard shortcuts](https://crbug.com/13891#c50). Which keyboard shortcuts are known depends on the user's system. Use the `keydown` event to implement keyboard shortcuts.

12

14

As of Firefox 65, the `keypress` event is no longer fired for [non-printable keys](<https://developer.mozilla.org/docs/Web/API/KeyboardEvent/keyCode#Non-printable_keys_(function_keys)>), except for the Enter key, and the Shift + Enter and Ctrl + Enter key combinations (these were kept for cross-browser compatibility purposes).

9

11.6

2

1

Chrome does not fire the `keypress` event for [known keyboard shortcuts](https://crbug.com/13891#c50). Which keyboard shortcuts are known depends on the user's system. Use the `keydown` event to implement keyboard shortcuts.

18

Chrome does not fire the `keypress` event for [known keyboard shortcuts](https://crbug.com/13891#c50). Which keyboard shortcuts are known depends on the user's system. Use the `keydown` event to implement keyboard shortcuts.

14

As of Firefox 65, the `keypress` event is no longer fired for [non-printable keys](<https://developer.mozilla.org/docs/Web/API/KeyboardEvent/keyCode#Non-printable_keys_(function_keys)>), except for the Enter key, and the Shift + Enter and Ctrl + Enter key combinations (these were kept for cross-browser compatibility purposes).

12

1

1.0

Samsung Internet does not fire the `keypress` event for [known keyboard shortcuts](https://crbug.com/13891#c50). Which keyboard shortcuts are known depends on the user's system. Use the `keydown` event to implement keyboard shortcuts.

`keyup_event`

1

12

14

9

11.6

2

1

18

14

12

1

1.0

`lastModified`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`lastStyleSheetSet`

No

No

3

No

No

No

No

No

4

No

No

No

`linkColor`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

1

4

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

4

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

`links`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`loadOverlay`

No

No

Yes-61

\["Available only to [XUL documents](https://developer.mozilla.org/docs/Mozilla/Tech/XUL).", "See [bug 1449791](https://bugzil.la/1449791)"\]

Yes-61

\["Available only to [XUL documents](https://developer.mozilla.org/docs/Mozilla/Tech/XUL).", "See [bug 1449791](https://bugzil.la/1449791)"\]

No

No

No

No

No

No

No

No

No

`location`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

`lostpointercapture_event`

57

≤79

59

?

44

13

57

57

79

43

13

7.0

`mozSetImageElement`

No

No

4

No

No

No

No

No

4

No

No

No

`mozSyntheticDocument`

No

No

8-23

No

No

No

No

No

8-23

No

No

No

`normalizeDocument`

No

No

1-7

No

No

No

No

No

4-7

No

No

No

`onafterscriptexecute`

No

No

9

No

No

No

No

No

9

No

No

No

`onbeforescriptexecute`

No

No

9

No

No

No

No

No

9

No

No

No

`oncopy`

1

17

9

No

≤12.1

2

1

18

9

≤12.1

1

1.0

`oncut`

1

17

9

No

≤12.1

2

1

18

9

≤12.1

1

1.0

`onfreeze`

68

79

No

No

55

No

68

68

No

48

No

10.0

`onfullscreenchange`

71

45

12

64

10

11

Yes

5.1

71

45

71

45

64

10

Yes

5.1

5.0

`onfullscreenerror`

71

45

12

64

10

11

Yes

6

71

45

71

45

64

10

Yes

6

5.0

`onpaste`

1

17

9

No

≤12.1

2

1

18

9

≤12.1

1

1.0

`onpointerlockchange`

36

13

50

No

23

10.1

37

36

50

24

No

3.0

`onpointerlockerror`

36

13

50

No

23

10.1

37

36

50

24

No

3.0

`onreadystatechange`

9

12

9

4

≤12.1

5.1

≤37

18

9

≤12.1

5

1.0

`onresume`

68

79

No

No

55

No

68

68

No

48

No

10.0

`onvisibilitychange`

62

Before Chrome 62, this event handler attribute is not supported; however, the event itself is supported since Chrome 33. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`.

18

Before Edge 18, this event handler attribute was not supported; however, the event itself was supported since Edge 12. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`.

56

No

This event handler attribute is not supported; however, the event itself is supported since IE 10. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`.

49

Before Opera 49, this event handler attribute is not supported; however, the event itself is supported since Opera 20. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`.

10.1

\["Doesn't fire the `visibilitychange` event when navigating away from a document, so also include code to check for the `pagehide` event (which does fire for that case in all current browsers). See WebKit bugs [116769](https://webkit.org/b/116769), [151234](https://webkit.org/b/151234), [151610](https://webkit.org/b/151610), and [194897](https://webkit.org/b/194897).", "Before Safari 10.1, this event handler attribute was not supported; however, the event itself was supported since Safari 7. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`."\]

62

Before WebView 62, this event handler attribute is not supported; however, the event itself is supported since WebView 4.4.3. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`.

62

Before Chrome 62, this event handler attribute is not supported; however, the event itself is supported since Chrome 33. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`.

56

46

Before Opera Android 46, this event handler attribute is not supported; however, the event itself is supported since Opera Android 20. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`.

10.3

\["Doesn't fire the `visibilitychange` event when navigating away from a document, so also include code to check for the `pagehide` event (which does fire for that case in all current browsers). See WebKit bugs [116769](https://webkit.org/b/116769), [151234](https://webkit.org/b/151234), [151610](https://webkit.org/b/151610), and [194897](https://webkit.org/b/194897).", "Before Safari iOS 10.3, this event handler attribute was not supported; however, the event itself was supported since Safari iOS 7. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`."\]

8.0

Before Samsung Internet 8.0, this event handler attribute is not supported; however, the event itself is supported since Samsung Internet 2.0. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`.

`open`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

1

4

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

4

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

`origin`

41-71

12-79

No

No

28-58

6.1-14

41-71

41-71

No

28-50

6.1-14

4.0-10.0

`paste_event`

1

12

Yes

11

15

Yes

1

18

Yes

14

?

1.0

`pictureInPictureEnabled`

69

79

No

No

56

13.1

No

No

No

No

13.4

No

`plugins`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

1

4

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

10.1

3-10.1

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

4

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

10.3

1-10.3

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

`pointercancel_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`pointerdown_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`pointerenter_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`pointerleave_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`pointerlockchange_event`

45

22-45

≤79

?

?

?

?

45

≤37-45

45

25-45

?

?

?

5.0

1.5-5.0

`pointerlockerror_event`

45

22-45

≤79

?

?

?

?

45

≤37-45

45

25-45

?

?

?

5.0

1.5-5.0

`pointermove_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`pointerout_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`pointerover_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`pointerup_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`popupNode`

No

No

Yes

Available only to [XUL documents](https://developer.mozilla.org/docs/Mozilla/Tech/XUL).

No

No

No

No

No

No

No

No

No

`preferredStyleSheetSet`

No

No

3

No

No

No

No

No

4

No

No

No

`queryCommandEnabled`

1

12

41

1-41

`queryCommandEnabled` with arguments `cut`, `copy` or `paste` would throw errors unless the script had special privileges.

4

≤12.1

2

1

18

41

4-41

`queryCommandEnabled` with arguments `cut`, `copy` or `paste` would throw errors unless the script had special privileges.

≤12.1

1

1.0

`queryCommandIndeterm`

1

12

1

4

15

2

1

18

4

14

1

1.0

`queryCommandState`

1

12

1

4

≤12.1

2

1

18

4

≤12.1

1

1.0

`queryCommandSupported`

1

12

41

1-41

`paste` argument incorrectly returned `true` when the paste feature was available but the calling script had insufficient privileges to actually perform the action.

4

≤12.1

2

1

18

41

4-41

`paste` argument incorrectly returned `true` when the paste feature was available but the calling script had insufficient privileges to actually perform the action.

≤12.1

1

1.0

`queryCommandText`

No

12-79

1-14

This method never did anything and always threw an exception.

4

No

No

No

No

4-14

This method never did anything and always threw an exception.

No

No

No

`queryCommandValue`

1

12

1

4

≤12.1

2

1

18

4

≤12.1

1

1.0

`readyState`

1

12

3.6

11

9-11

Internet Explorer 9 and 10 have bugs where the 'interactive' state can be fired too early before the document has finished parsing.

4-9

Only supports 'complete'.

11

Opera Presto fires 'complete' late after the 'load' event (in an incorrect order as per HTML5 standard specification).

1

1

18

4

11

Opera Presto fires 'complete' late after the 'load' event (in an incorrect order as per HTML5 standard specification).

1

1.0

`readystatechange_event`

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

`referrer`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

`registerElement`

33-80

79-80

31-59

No

23-67

No

4.4.3-80

33-80

31-59

24-57

No

3.0-13.0

`releaseCapture`

No

No

4

5

No

No

No

No

4

No

No

No

`releaseEvents`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

1

11

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

4

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

`requestStorageAccess`

78

85

65

No

65

11.1

No

78

65

No

11.3

No

`routeEvent`

No

No

1-25

No

No

No

No

No

4-25

No

No

No

`scripts`

1

12

9

4

≤12.1

3

1

18

9

≤12.1

1

1.0

`scroll_event`

1

12

6

9

11.6

2

1

18

6

12

1

1.0

`scrollingElement`

44

12

48

No

31

9

44

44

48

32

9

4.0

`selectedStyleSheetSet`

No

No

3

No

No

No

No

No

4

No

No

No

`selectionchange_event`

Yes

12

52

Yes

?

1.3

Yes

Yes

52

?

Yes

Yes

`selectstart_event`

Yes

12

52

Yes

?

1.3

Yes

Yes

52

?

No

Yes

`styleSheetSets`

No

No

3

No

No

No

No

No

4

No

No

No

`timeline`

84

84

75

No

70

13.1

84

84

79

63-79

60

13.4

14.0

`title`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`tooltipNode`

No

No

Yes

Available only to [XUL documents](https://developer.mozilla.org/docs/Mozilla/Tech/XUL).

No

No

No

No

No

No

No

No

No

`touchcancel_event`

22

12

52

No

No

No

≤37

25

6

Yes

Yes

1.5

`touchend_event`

22

12

52

No

No

No

≤37

25

6

Yes

Yes

1.5

`touchmove_event`

22

12

52

No

No

No

≤37

25

6

Yes

Yes

1.5

`touchstart_event`

22

12

52

No

No

No

≤37

25

6

Yes

Yes

1.5

`transitioncancel_event`

No

No

53

?

?

13.1

12

No

No

53

?

13.4

12

No

`transitionend_event`

No

No

51

?

?

Yes

No

No

51

?

Yes

No

`transitionrun_event`

No

No

53

?

?

13.1

12

No

No

53

?

13.4

12

No

`transitionstart_event`

No

No

53

?

?

13.1

12

No

No

53

?

13.4

12

No

`undoManager`

No

No

No

No

No

No

No

No

No

No

No

No

`visibilitychange_event`

33

Before Chrome 62, the `onvisibilitychange` attribute is not supported. To listen to this event in earlier versions of Chrome, use `document.addEventListener('visibilitychange', function() {});`.

13

12

Before Edge 18, the `onvisibilitychange` attribute is not supported. To listen to this event in earlier versions of Edge, use `document.addEventListener('visibilitychange', function() {});`.

56

10

The `onvisibilitychange` attribute is not supported in IE. To listen to this event, use `document.addEventListener('visibilitychange', function() {});`.

20

Before Opera 49, the `onvisibilitychange` attribute is not supported. To listen to this event in earlier versions of Opera, use `document.addEventListener('visibilitychange', function() {});`.

15

12.1-15

7

\["Doesn't fire the `visibilitychange` event when navigating away from a document, so also include code to check for the `pagehide` event (which does fire for that case in all current browsers). See WebKit bugs [116769](https://webkit.org/b/116769), [151234](https://webkit.org/b/151234), [151610](https://webkit.org/b/151610), and [194897](https://webkit.org/b/194897).", "Before Safari 14, the event does not bubble, so `document.addEventListener('visibilitychange', ...)` works, but `window.addEventListener('visibilitychange', ...)` does not.", "Before Safari 10.1, the `onvisibilitychange` attribute is not supported. To listen to this event in earlier versions of Safari, use `document.addEventListener('visibilitychange', function() {});`."\]

4.4.3

Before WebView 62, the `onvisibilitychange` attribute is not supported. To listen to this event in earlier versions of WebView, use `document.addEventListener('visibilitychange', function() {});`.

≤37

33

Before Chrome 62, the `onvisibilitychange` attribute is not supported. To listen to this event in earlier versions of Chrome, use `document.addEventListener('visibilitychange', function() {});`.

18

56

20

Before Opera Android 46, the `onvisibilitychange` attribute is not supported. To listen to this event in earlier versions of Opera Android, use `document.addEventListener('visibilitychange', function() {});`.

14

12.1-14

7

\["Doesn't fire the `visibilitychange` event when navigating away from a document, so also include code to check for the `pagehide` event (which does fire for that case in all current browsers). See WebKit bugs [116769](https://webkit.org/b/116769), [151234](https://webkit.org/b/151234), [151610](https://webkit.org/b/151610), and [194897](https://webkit.org/b/194897).", "Before Safari iOS 14, the event does not bubble, so `document.addEventListener('visibilitychange', ...)` works, but `window.addEventListener('visibilitychange', ...)` does not.", "Before Safari iOS 10.3, the `onvisibilitychange` attribute is not supported. To listen to this event in earlier versions of Safari iOS, use `document.addEventListener('visibilitychange', function() {});`."\]

2.0

Before Samsung Internet 8.0, the `onvisibilitychange` attribute is not supported. To listen to this event in earlier versions of Samsung Internet, use `document.addEventListener('visibilitychange', function() {});`.

1.0

`visibilityState`

33

13

12

18

10-52

10

20

15

12.1-15

6.1

4.4.3

≤37

33

18

18

10-52

20

14

12.1-14

7

2.0

1.0

`vlinkColor`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

1

4

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

4

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

`wasDiscarded`

68

79

No

No

55

No

68

68

No

48

No

10.0

`wheel_event`

61

12

Yes

Yes

48

6.1

61

61

Yes

45

No

8.0

`width`

1-31

No

1-6

No

15-18

1-10

1-4.4.3

18-31

4-6

14-18

1-10

1.0-3.0

`write`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

`writeln`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

1

4

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

4

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

`xmlEncoding`

1

12

1-10

9

15

3

1

18

4-10

14

1

1.0

`xmlStandalone`

1

12

1-10

9

15

3

1

18

4-10

14

1

1.0

`xmlVersion`

1

12

1-10

9

15

3

1

18

4-10

14

1

1.0

`activeElement`

1

12

3

6

≤12.1

4

1

18

4

≤12.1

3.2

1.0

`adoptedStyleSheets`

73

79

No

No

60

No

73

73

No

50

No

11.0

`elementFromPoint`

1

Before Chrome 66, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

12

3

4

≤12.1

Before Opera 53, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

4

1

Before WebView 66, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

18

Before Chrome 66, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

4

≤12.1

Before Opera Android 47, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

3.2

1.0

Before Samsung Internet 9.0, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

`elementsFromPoint`

43

Before Chrome 66, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

79

12-79

Returns a `NodeList` instead of an array. See [the MSDN documentation](<https://msdn.microsoft.com/en-us/library/hh772121(v=vs.85).aspx>). Returns `null` when the point provided has no elements beneath it (e.g., when given a point outside the document).

46

10

Returns a `NodeList` instead of an array. See [the MSDN documentation](<https://msdn.microsoft.com/en-us/library/hh772121(v=vs.85).aspx>). Returns `null` when the point provided has no elements beneath it (e.g., when given a point outside the document).

30

11.1

43

Before WebView 66, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

43

Before Chrome 66, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

46

30

11.3

4.0

Before Samsung Internet 9.0, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

`fullscreenElement`

71

53

≤79

≤18

12

64

9

Yes

58

40

Yes

71

53

71

53

64

9

50

41

12

Full-screen mode is only supported on the iPad.

10.0

6.0

`getAnimations`

84

61

Implements an older version of the specification.

84

79

Implements an older version of the specification.

75

63-75

No

70

48

Implements an older version of the specification.

14

13.1

Implements an older version of the specification, see Webkit bug [179536](https://webkit.org/b/179536).

84

84

61

Implements an older version of the specification.

79

60

45

Implements an older version of the specification.

14

13.4

Implements an older version of the specification, see Webkit bug [179536](https://webkit.org/b/179536).

14.0

`pictureInPictureElement`

69

79

No

No

56

13.1

No

No

No

No

13.4

No

`pointerLockElement`

37

12

50

No

24

10.1

37

37

50

24

No

3.0

`styleSheets`

1

12

1

4

≤12.1

4

1

18

4

≤12.1

3.2

1.0

`append`

54

17

49

No

41

10

54

54

49

41

10

6.0

`childElementCount`

29

17

25

No

16

9

≤37

29

25

16

9

2.0

`children`

29

16

25

No

16

9

≤37

29

25

16

9

2.0

`firstElementChild`

29

17

25

No

16

9

≤37

29

25

16

9

2.0

`lastElementChild`

29

17

25

No

16

9

≤37

29

25

16

9

2.0

`prepend`

54

17

49

No

41

10

54

54

49

41

10

6.0

`querySelector`

1

12

3.5

9

8

`querySelectorAll()` is supported, but only for CSS 2.1 selectors.

10

3.1

1

18

4

10.1

2

1.0

`querySelectorAll`

1

12

3.5

9

8

`querySelectorAll()` is supported, but only for CSS 2.1 selectors.

10

3.1

1

18

4

10.1

2

1.0

`replaceChildren`

86

86

78

No

72

14

86

86

79

61

14

14.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document</a>
