# GlobalEventHandlers

The `GlobalEventHandlers` mixin describes the event handlers common to several interfaces like [`HTMLElement`](htmlelement), [`Document`](document), or [`Window`](window). Each of these interfaces can, of course, add more event handlers in addition to the ones listed below.

**Note**: `GlobalEventHandlers` is a mixin and not an interface; you can't actually create an object of type `GlobalEventHandlers`.

## Properties

_This interface doesn't include any properties except for the event handlers listed below._

### Event handlers

These event handlers are defined on the [`GlobalEventHandlers`](globaleventhandlers) mixin, and implemented by [`HTMLElement`](htmlelement), [`Document`](document), [`Window`](window), as well as by [`WorkerGlobalScope`](workerglobalscope) for Web Workers.

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

## Methods

_This interface defines no methods._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/">Selection API<br />
<span class="small">The definition of 'Extension to GlobalEventHandlers' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds <code>onselectionchange.</code></td></tr><tr class="even"><td><a href="https://w3c.github.io/pointerlock/#extensions-to-the-document-interface">Pointer Lock<br />
<span class="small">The definition of 'Extension of Document' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds <code>onpointerlockchange</code> and <code>onpointerlockerror</code> on <a href="document"><code>Document</code></a>. It is experimentally implemented on <code>GlobalEventHandlers</code>.</td></tr><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#globaleventhandlers">HTML Living Standard<br />
<span class="small">The definition of 'GlobalEventHandlers' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change since the latest snapshot, <a href="https://www.w3.org/TR/html51/">HTML 5.1</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/#globaleventhandlers">HTML 5.1<br />
<span class="small">The definition of 'GlobalEventHandlers' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>. Added <code>onsort</code> since the <a href="https://www.w3.org/TR/html52/">HTML5</a> snapshot.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/#globaleventhandlers">HTML5<br />
<span class="small">The definition of 'GlobalEventHandlers' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>. Creation of <code>GlobalEventHandlers</code> (properties where on the target before it).</td></tr></tbody></table>

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

`GlobalEventHandlers`

1

12

1

4

Yes

1

1

18

4

Yes

1

1.0

`onabort`

1

12

9

9

≤12.1

1

1

18

9

≤12.1

1

1.0

`onanimationcancel`

No

No

54

?

?

13.1

12

The event handler is exposed but will not actually be called unless both the "Web Animations" and "CSS Animations via Web Animations" preferences are enabled.

No

No

54

?

13.4

12

The event handler is exposed but will not actually be called unless both the "Web Animations" and "CSS Animations via Web Animations" preferences are enabled.

No

`onanimationend`

79

Yes

18

≤79

51

No

66

9

79

Yes

79

Yes

51

57

9

12.0

Yes

`onanimationiteration`

79

Yes

18

≤79

51

No

66

9

79

Yes

79

Yes

51

57

9

12.0

Yes

`onanimationstart`

79

Yes

18

≤79

51

No

66

9

79

Yes

79

Yes

51

57

9

12.0

Yes

`onauxclick`

55

79

53

No

42

No

55

55

53

42

No

6.0

`onblur`

1

12

9

9

≤12.1

1

1

18

9

≤12.1

1

1.0

`oncancel`

32

79

No

No

19

No

4.4.3

32

No

19

No

2.0

`oncanplay`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

`oncanplaythrough`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

`onchange`

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

1

1.0

`onclick`

1

12

1

4

9

3

1

18

4

10.1

1

1.0

`onclose`

32

79

53

No

19

No

4.4.3

32

53

19

No

2.0

`oncontextmenu`

1

12

9

5

≤12.1

4

1

18

9

≤12.1

3.2

1.0

`oncuechange`

32

18

68

Added for the `<track>` element (`HTMLTrackElement`) in Firefox 68.

31

Added for the `TextTrack` interface in Firefox 31.

No

19

≤12.1-15

10.1

4.4.3

32

68

Added for the `<track>` element (`HTMLTrackElement`) in Firefox 68.

31

Added for the `TextTrack` interface in Firefox 31.

19

≤12.1-14

10.3

2.0

`ondblclick`

1

12

9

4

≤12.1

1

1

18

9

≤12.1

1

1.0

`ondrag`

1

12

9

9

12

3.1

1

18

9

12

2

1.0

`ondragend`

1

12

9

9

12

3.1

1

18

9

12

2

1.0

`ondragenter`

1

12

9

9

12

3.1

1

18

9

12

2

1.0

`ondragexit`

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

`ondragleave`

1

12

9

9

12

3.1

1

18

9

12

2

1.0

`ondragover`

1

12

9

9

12

3.1

1

18

9

12

2

1.0

`ondragstart`

1

12

9

9

12

3.1

1

18

9

12

2

1.0

`ondrop`

1

12

9

9

12

3.1

1

18

9

12

2

1.0

`ondurationchange`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

`onemptied`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

`onended`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

`onerror`

10

12

1

9

11.6

6

≤37

18

4

12

6

1.0

`onfocus`

1

12

9

9

≤12.1

1

1

18

9

≤12.1

1

1.0

`onformdata`

77

79

72

No

64

No

77

77

79

55

No

12.0

`ongotpointercapture`

57

17

59

No

44

13

57

57

79

43

13

7.0

`oninput`

1

12

9

9

10

4

1

18

9

10.1

3.2

1.0

`oninvalid`

4

13

9

No

≤12.1

5

≤37

18

9

≤12.1

4

1.0

`onkeydown`

1

12

9

4

≤12.1

1

1

18

9

≤12.1

1

1.0

`onkeypress`

1

12

9

4

≤12.1

1

1

18

9

≤12.1

1

1.0

`onkeyup`

1

12

9

4

≤12.1

1

1

18

9

≤12.1

1

1.0

`onload`

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

1

1.0

`onloadeddata`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

`onloadedmetadata`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

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

`onlostpointercapture`

57

17

59

No

44

13

57

57

79

43

13

7.0

`onmousedown`

1

12

9

4

≤12.1

1

1

18

9

≤12.1

1

1.0

`onmouseenter`

30

12

10

5.5

17

6.1

4.4

30

10

18

7

2.0

`onmouseleave`

30

12

10

5.5

17

6.1

4.4

30

10

18

7

2.0

`onmousemove`

1

12

9

4

≤12.1

1

1

18

9

≤12.1

1

1.0

`onmouseout`

1

12

9

4

≤12.1

1

1

18

9

≤12.1

1

1.0

`onmouseover`

1

12

9

4

≤12.1

1

1

18

9

≤12.1

1

1.0

`onmouseup`

1

12

9

4

≤12.1

1

1

18

9

≤12.1

1

1.0

`onmousewheel`

Yes

≤79

No

?

?

?

Yes

Yes

No

?

?

Yes

`onpause`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

`onplay`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

`onplaying`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

`onpointercancel`

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

`onpointerdown`

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

`onpointerenter`

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

`onpointerleave`

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

`onpointermove`

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

`onpointerout`

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

`onpointerover`

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

`onpointerup`

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

`onprogress`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

`onratechange`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

`onreset`

1

12

9

9

≤12.1

1

1

18

9

≤12.1

1

1.0

`onresize`

34

79

12-79

In EdgeHTML versions of Edge, this handler was only supported on the [`Window`](https://developer.mozilla.org/docs/Web/API/Window) API.

38

4

In Internet Explorer, this handler was only supported on the [`Window`](https://developer.mozilla.org/docs/Web/API/Window) API.

21

10.1

37

34

38

21

10.3

2.0

`onscroll`

1

12

9

9

≤12.1

1.3

1

18

9

≤12.1

1

1.0

`onseeked`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

`onseeking`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

`onselect`

1

12

9

9

≤12.1

1

1

18

9

≤12.1

1

1.0

`onselectionchange`

11

12

52

5.5

15

5.1

≤37

18

52

14

5

1.0

`onselectstart`

1

12

52

4

15

1.3

1

18

52

14

1

The `selectstart` event never fires and never invokes this handler.

1.0

`onshow`

No

No

Yes

?

?

?

No

No

Yes

?

?

No

`onsort`

No

No

No

?

?

?

No

No

No

?

?

No

`onstalled`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

`onsubmit`

1

12

9

9

≤12.1

1

1

18

9

≤12.1

1

1.0

`onsuspend`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

`ontimeupdate`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

`ontouchcancel`

No

No

No

No

No

No

≤37

18

Yes

≤14

≤3

1.0

`ontouchend`

No

No

No

No

No

No

≤37

18

Yes

≤14

≤3

1.0

`ontouchmove`

No

No

No

No

No

No

≤37

18

Yes

≤14

≤3

1.0

`ontouchstart`

No

No

No

No

No

No

≤37

18

Yes

≤14

≤3

1.0

`ontransitioncancel`

87

87

53

No

73

13.1

12

The event handler is exposed but will not actually be called unless both the "Web Animations" and "CSS Animations via Web Animations" preferences are enabled.

87

87

53

No

13.4

12

The event handler is exposed but will not actually be called unless both the "Web Animations" and "CSS Animations via Web Animations" preferences are enabled.

14.0

`ontransitionend`

79

Yes

18

≤79

51

No

66

11

79

Yes

79

Yes

51

57

11

11.0

Yes

`ontransitionrun`

87

87

53

No

73

13.1

12

The event handler is exposed but will not actually be called unless both the "Web Animations" and "CSS Animations via Web Animations" preferences are enabled.

87

87

53

No

13.4

12

The event handler is exposed but will not actually be called unless both the "Web Animations" and "CSS Animations via Web Animations" preferences are enabled.

14.0

`ontransitionstart`

87

87

53

No

73

13.1

12

The event handler is exposed but will not actually be called unless both the "Web Animations" and "CSS Animations via Web Animations" preferences are enabled.

87

87

53

No

13.4

12

The event handler is exposed but will not actually be called unless both the "Web Animations" and "CSS Animations via Web Animations" preferences are enabled.

14.0

`onvolumechange`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

`onwaiting`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

`onwheel`

31

12

17

No

18

7

4.4.3

31

17

18

7

2.0

## See also

- [`Element`](element)
- [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers)
- [`Event`](event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers</a>
