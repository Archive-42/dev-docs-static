# InputEvent.getTargetRanges()

The `getTargetRanges()` method of the [`InputEvent`](../inputevent) interface returns an array of static ranges that will be affected by a change to the DOM if the input event is not canceled.

This allows web apps to override text edit behavior before the browser modifies the DOM tree, and provides more control over input events to improve performance.

## Syntax

    var staticRanges[] = inputEvent.getTargetRanges()

### Parameters

None.

### Return value

An array of [`StaticRange`](../staticrange) objects.

## Examples

### Feature Detection

The following function returns true if `beforeinput`, and thus `getTargetRanges`, is supported.

    function isBeforeInputEventAvailable() {
      return window.InputEvent && typeof InputEvent.prototype.getTargetRanges === "function";
    }

### Basic usage

The following example selects a `contenteditable` element and utilizes the `beforeinput` event to log the result of `getTargetRanges()`.

    const editableElem = document.querySelector('[contenteditable="true"]');

    editableElem.addEventListener('beforeinput', (e) => {
        const targetRanges = e.getTargetRanges();
        console.log(targetRanges);
    })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/input-events/#dom-inputevent-gettargetranges">Input Events Level 2<br />
<span class="small">The definition of 'getTargetRanges()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getTargetRanges`

60

79

87

75-87

No

47

10.1

60

60

87

79-87

44

10.3

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/getTargetRanges" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/getTargetRanges</a>
