# Document.createTouch()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Note:** Before Gecko 25.0, this method was defined on the [`DocumentTouch`](../documenttouch) mixin.

The `Document.createTouch()` method <span class="seosummary">creates and returns a new [`Touch`](../touch) object.</span>

## Syntax

    var touch = DocumentTouch.createTouch(view, target, identifier, pageX, pageY,
                                          screenX, screenY);

### Parameters

**Note:** All parameters are optional.

`view`  
The [`window`](../window) in which the touch occurred.

`target`  
The [`EventTarget`](../eventtarget) for the touch.

`identifier`  
The value for [`Touch.identifier`](../touch/identifier).

`pageX`  
The value for [`Touch.pageX`](../touch/pagex).

`pageY`  
The value for [`Touch.pageY`](../touch/pagey).

`screenX`  
The value for [`Touch.screenX`](../touch/screenx).

`screenY`  
The value for [`Touch.screenY`](../touch/screeny).

**Note:** Previous versions of this method included the following additional parameters but those parameters are not included in either of the standards listed below. Consequently, these parameters should be considered deprecated and not used.

`clientX`  
The value for [`Touch.clientX`](../touch/clientx).

`clientY`  
The value for [`Touch.clientY`](../touch/clienty).

`radiusX`  
The value for [`Touch.radiusX`](../touch/radiusx).

`radiusY`  
The value for [`Touch.radiusY`](../touch/radiusy).

`rotationAngle`  
The value for [`Touch.rotationAngle`](../touch/rotationangle).

`force`  
The value for [`Touch.force`](../touch/force).

### Return value

`touch`  
A [`Touch`](../touch) object configured as described by the input parameters.

## Example

This example illustrates using the [`Document.createTouch()`](createtouch) method to create [`Touch`](../touch) objects.

In following code snippet, two [`Touch`](../touch) objects are created for the `target` element.

    var target = document.getElementById("target");

    var touch1 = document.createTouch(window, target, 1, 15, 20, 35, 40);
    var touch2 = document.createTouch(window, target, 2, 25, 30, 45, 50);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/touch-events/#widl-Document-createTouch-Touch-WindowProxy-view-EventTarget-target-long-identifier-long-pageX-long-pageY-long-screenX-long-screenY">Touch Events<br />
<span class="small">The definition of 'Document.createTouch()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [Touch events](../touch_events)
- [`TouchList`](../touchlist)
- [`Touch`](../touch)
- [`Document.createTouchList()`](createtouchlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/createTouch" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/createTouch</a>
