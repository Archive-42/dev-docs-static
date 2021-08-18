# Element.ariaSetSize

The `ariaSetSize` property of the [`Element`](../element) interface reflects the value of the `aria-setsize` attribute, which defines the number of items in the current set of listitems or treeitems.

## Syntax

    var ariaSetSize = element.ariaSetSize;
    element.ariaSetSize = ariaSetSize

### Value

A [`DOMString`](../domstring) containing an integer.

## Examples

In this example the `aria-setsize` attribute on the element with an ID of `tab-id` is set to "3", to inform a device that there are currently 3 tabs in the group. Using `ariaSetSize` we update the value to "4".

    <button role="tab" aria-selected="true" aria-setsize="3" aria-controls="tabpanel-id" id="tab-id">Tab label</button>

    let el = document.getElementById('tab-id');
    console.log(el.ariaSetSize); // 3
    el.ariaSetSize = "4";
    console.log(el.ariaSetSize); // 4

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariasetsize">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaSetSize' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaSetSize`

84

84

No

No

70

12.1

84

84

No

60

12.2

14.0

## See also

- [ARIA: tab role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Tab_Role)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaSetSize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaSetSize</a>
