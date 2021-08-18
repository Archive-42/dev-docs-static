# CustomEvent

The `CustomEvent` interface represents events initialized by an application for any purpose.

**Note:** This feature is available in [Web Workers](web_workers_api).

## Constructor

[`CustomEvent()`](customevent/customevent)  
Creates a `CustomEvent`.

## Properties

[`CustomEvent.detail`](customevent/detail) <span class="badge inline readonly">Read only </span>  
Any data passed when initializing the event.

_This interface inherits properties from its parent,_ [`Event`](event):

[`Event.bubbles`](event/bubbles) <span class="badge inline readonly">Read only </span>  
A boolean indicating whether or not the event bubbles up through the DOM.

[`Event.cancelBubble`](event/cancelbubble)  
A historical alias to [`Event.stopPropagation()`](event/stoppropagation). Setting its value to `true` before returning from an event handler prevents propagation of the event.

[`Event.cancelable`](event/cancelable) <span class="badge inline readonly">Read only </span>  
A boolean indicating whether the event is cancelable.

[`Event.composed`](event/composed) <span class="badge inline readonly">Read only </span>  
A boolean indicating whether or not the event can bubble across the boundary between the shadow DOM and the regular DOM.

[`Event.currentTarget`](event/currenttarget) <span class="badge inline readonly">Read only </span>  
A reference to the currently registered target for the event. This is the object to which the event is currently slated to be sent. It's possible this has been changed along the way through _retargeting_.

[`Event.deepPath`](event/composedpath) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of DOM [`Node`](node)s through which the event has bubbled.

[`Event.defaultPrevented`](event/defaultprevented) <span class="badge inline readonly">Read only </span>  
Indicates whether or not the call to [`event.preventDefault()`](event/preventdefault) canceled the event.

[`Event.eventPhase`](event/eventphase) <span class="badge inline readonly">Read only </span>  
Indicates which phase of the event flow is being processed.

[`Event.explicitOriginalTarget`](event/explicitoriginaltarget) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>  
The explicit original target of the event (Mozilla-specific.)

[`Event.originalTarget`](event/originaltarget) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>  
The original target of the event, before any retargetings. (Mozilla-specific.)

[`Event.returnValue`](event/returnvalue) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A historical property introduced by Internet Explorer and eventually adopted into the DOM specification in order to ensure existing sites continue to work. Ideally, you should try to use [`Event.preventDefault()`](event/preventdefault) and [`Event.defaultPrevented`](event/defaultprevented) instead, but you can use `returnValue` if you choose to do so.

[`Event.srcElement`](event/srcelement) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
A non-standard alias (from old versions of Microsoft Internet Explorer) for [`Event.target`](event/target). Some other browsers are starting to support it for web compatibility purposes.

[`Event.target`](event/target) <span class="badge inline readonly">Read only </span>  
A reference to the target to which the event was originally dispatched.

[`Event.timeStamp`](event/timestamp) <span class="badge inline readonly">Read only </span>  
The time at which the event was created (in milliseconds). By specification, this value is time since epoch—but in reality, browsers' definitions vary. In addition, work is underway to change this to be a [`DOMHighResTimeStamp`](domhighrestimestamp) instead.

[`Event.type`](event/type) <span class="badge inline readonly">Read only </span>  
The name of the event. Case-insensitive.

[`Event.isTrusted`](event/istrusted) <span class="badge inline readonly">Read only </span>  
Indicates whether or not the event was initiated by the browser (after a user click, for instance) or by a script (using an event creation method, like [`Event.initEvent`](event/initevent)).

### Deprecated properties

[`Event.scoped`](event/composed) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the given event will bubble across through the shadow root into the standard DOM. Use [`composed`](event/composed) instead.

## Methods

[`CustomEvent.initCustomEvent()`](customevent/initcustomevent) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Initializes a `CustomEvent` object. If the event has already being dispatched, this method does nothing.

_This interface inherits methods from its parent,_ [`Event`](event):

[`Event.composedPath()`](event/composedpath)  
Returns the event’s path (objects on which listeners will be invoked). This does not include nodes in shadow trees if the shadow root was created with its [`ShadowRoot.mode`](shadowroot/mode) closed.

[`Event.preventDefault()`](event/preventdefault)  
Cancels the event (if it is cancelable).

[`Event.stopImmediatePropagation()`](event/stopimmediatepropagation)  
For this particular event, prevent all other listeners from being called. This includes listeners attached to the same element as well as those attached to elements that will be traversed later (during the capture phase, for instance).

[`Event.stopPropagation()`](event/stoppropagation)  
Stops the propagation of events further along in the DOM.

### Deprecated methods

[`Event.initEvent()`](event/initevent) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Initializes the value of an Event created. If the event has already been dispatched, this method does nothing.

<span class="page-not-created">`Event.getPreventDefault()`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns the value of [`Event.defaultPrevented`](event/defaultprevented).

<span class="page-not-created">`Event.preventBubble()`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Prevents the event from bubbling. Use [`event.stopPropagation`](event/stoppropagation) instead.

<span class="page-not-created">`Event.preventCapture()`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Prevents the event from bubbling. Use [`event.stopPropagation`](event/stoppropagation) instead.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-customevent">DOM<br />
<span class="small">The definition of 'CustomEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CustomEvent`

15

12

6

9

11

5.1

≤37

18

6

11

6

1.0

`CustomEvent`

15

12

11

No

11.6

6.1

≤37

18

14

12

6.1

1.0

`detail`

15

12

11

No

11.6

6.1

≤37

Yes

14

Yes

6.1

Yes

`initCustomEvent`

Yes

59

`canBubble`, `cancelable`, and `detail` are optional parameters defaulting to `false`, `false`, and `null` respectively.

12

6

9

11

5.1

Yes

59

`canBubble`, `cancelable`, and `detail` are optional parameters defaulting to `false`, `false`, and `null` respectively.

Yes

59

`canBubble`, `cancelable`, and `detail` are optional parameters defaulting to `false`, `false`, and `null` respectively.

6

Yes

Yes

Yes

7.0

`canBubble`, `cancelable`, and `detail` are optional parameters defaulting to `false`, `false`, and `null` respectively.

`worker_support`

Yes

12

48

Yes

Yes

Yes

Yes

Yes

48

Yes

Yes

Yes

## Firing from privileged code to non-privileged code

When firing a `CustomEvent` from privileged code (i.e. an extension) to non-privileged code (i.e. a webpage), security issues should be considered. Firefox and other Gecko applications restrict an object created in one context from being directly used for another, which will automatically prevent security holes, but these restrictions may also prevent your code from running as expected.

While creating a `CustomEvent` object, you must create the object from the same [window](https://developer.mozilla.org/en-US/docs/XUL/window). The `detail` attribute of your `CustomEvent` will be subjected to the same restrictions. `String` and `Array` values will be readable by the content without restrictions, but custom `Object` will not. While using a custom object, you will need to define the attributes of that object that are readable from the content script using [Components.utils.cloneInto()](https://developer.mozilla.org/en-US/docs/Mozilla/Tech/XPCOM/Language_Bindings/Components.utils.cloneInto).

    // doc is a reference to the content document
    function dispatchCustomEvent(doc) {
      var eventDetail = Components.utils.cloneInto({foo: 'bar'}, doc.defaultView);
      var myEvent = doc.defaultView.CustomEvent("mytype", eventDetail);
      doc.dispatchEvent(myEvent);
    }

But one needs to keep in mind that exposing a function will allow the content script to run it with chrome privileges, which can open a security vulnerability.

## See also

- [`Window.postMessage()`](window/postmessage)
- [Interaction between privileged and non-privileged pages](https://developer.mozilla.org/en-US/docs/Code_snippets/Interaction_between_privileged_and_non-privileged_pages)
- [Creating and triggering events](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent</a>
