VRDisplayEvent.VRDisplayEvent()
===============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The [`VRDisplayEvent`](../vrdisplayevent) constructor creates a `VRDisplayEvent` object instance.

Syntax
------

    var myEventObject = new VRDisplayEvent(type, eventInitDict);

### Parameters

*type*  
A [`DOMString`](../domstring) describing the type of event object you want to create.

*eventInitDict*  
A object containing initialization options to use when creating the constructor. These are:

`display`  
A property containing the [`VRDisplay`](../vrdisplay) the event is to be associated with.

`reason`  
A property containing a string representing the human-readable reason why the event is to be fired (see [`VRDisplayEvent.reason`](reason)).

Examples
--------

    var myEventObject = new VRDisplayEvent('custom', {
      display: vrDisplay,
      reason: 'Custom reason'
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-vrdisplayevent-vrdisplayevent">WebVR 1.1<br />
<span class="small">The definition of 'VRDisplayEvent()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`VRDisplayEvent`

No

≤18-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

See also
--------

-   [WebVR API homepage](../webvr_api)
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRDisplayEvent/VRDisplayEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRDisplayEvent/VRDisplayEvent</a>
