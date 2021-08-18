# CustomEvent.initCustomEvent()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `CustomEvent.initCustomEvent()` method initializes a `CustomEvent` object. If the event has already been dispatched, this method does nothing.

Events initialized in this way must have been created with the [`Document.createEvent()`](../document/createevent) method. This method must be called to set the event before it is dispatched, using [`EventTarget.dispatchEvent()`](../eventtarget/dispatchevent). Once dispatched, it doesn't do anything anymore.

**Note**

**Do not use this method anymore, as it is deprecated.**

Rather than using the feature, instead use specific event constructors, like [`CustomEvent()`](customevent). The page on [Creating and triggering events](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events) gives more information about the way to use those.

## Syntax

    event.initCustomEvent(type, canBubble, cancelable, detail);

### Parameters

`type`  
Is a [`DOMString`](../domstring) containing the name of the event.

_`canBubble`_  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the event bubbles up through the DOM or not.

`cancelable`  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the event is cancelable.

_`detail`_  
The data passed when initializing the event.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-customevent-initcustomevent">DOM<br />
<span class="small">The definition of 'CustomEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition, but already deprecated in favor of the use of a constructor, <a href="customevent"><code>CustomEvent()</code></a></td></tr></tbody></table>

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

## See also

- [`CustomEvent`](../customevent)
- The constructor to use instead of this deprecated method: [`CustomEvent()`](customevent).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent/initCustomEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent/initCustomEvent</a>
