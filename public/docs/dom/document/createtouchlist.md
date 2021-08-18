# Document.createTouchList()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Note:** Before Gecko 25.0, this method was defined on the [`DocumentTouch`](../documenttouch) mixin.

The `Document.createTouchList()` method <span class="seosummary">creates and returns a new [`TouchList`](../touchlist) object.</span>

## Syntax

    var list = DocumentTouch.createTouchList([touch1 [, touch2 [, ...]]]);

### Parameters

`touches`  
Zero or more [`Touch`](../touch) objects. **Note:** Firefox also accepts an [array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`Touch`](../touch) objects.

### Return value

`list`  
A [`TouchList`](../touchlist) object containing the [`Touch`](../touch) objects specified by the `touches` parameter.

## Example

This example illustrates using the [`Document.createTouchList()`](createtouchlist) method to create [`TouchList`](../touchlist) objects.

In following code snippet, some [`Touch`](../touch) objects are created for the `target` element and those touch points are then used to create some [`TouchList`](../touchlist) objects.

    var target = document.getElementById("target");

    // Create some touch points
    var touch1 = document.createTouch(window, target, 1, 15, 20, 35, 40);
    var touch2 = document.createTouch(window, target, 2, 25, 30, 45, 50);

    // Create an empty TouchList objects
    var list0 = document.createTouchList();

    // Create a TouchList with only one Touch object
    var list1 = document.createTouchList(touch1);

    // Create a list with two Touch objects
    var list2 = document.createTouchList(touch1, touch2);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/touch-events/#widl-Document-createTouchList-TouchList-Touch-touches">Touch Events<br />
<span class="small">The definition of 'Document.createTouchList()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [Touch events](../touch_events)
- [`Touch`](../touch)
- [`TouchEvent`](../touchevent)
- [`TouchList`](../touchlist)
- [`Document.createTouch()`](createtouch)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/createTouchList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/createTouchList</a>
