# HTMLOrForeignElement.tabIndex

The `tabIndex` property of the [`HTMLOrForeignElement`](../htmlorforeignelement) mixin represents the tab order of the current element.

Tab order is as follows:

1.  Elements with a positive `tabIndex`. Elements that have identical `tabIndex` values should be navigated in the order they appear. Navigation proceeds from the lowest `tabIndex` to the highest `tabIndex`.
2.  Elements that do not support the `tabIndex` attribute or support it and assign `tabIndex` to `0`, in the order they appear.

Elements that are disabled do not participate in the tabbing order.

Values don't need to be sequential, nor must they begin with any particular value. They may even be negative, though each browser trims very large values.

## Syntax

    element.tabIndex = index;
    var index = element.tabIndex;

### Value

`index` is an integer

## Example

    const b1 = document.getElementById('button1');

    b1.tabIndex = 1;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-tabindex">HTML Living Standard<br />
<span class="small">The definition of 'tabindex' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-HTML/">Document Object Model (DOM) Level 2 HTML Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-40676705">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'tabindex' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-40676705">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'tabindex' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`tabIndex`

1

18

12

Returns incorrect value for elements without an explicit tabindex attribute. See [issue 4365703](https://developer.microsoft.com/microsoft-edge/platform/issues/4365703/) for details.

1

5.5

Returns incorrect value for elements without an explicit tabindex attribute. See [issue 4365703](https://developer.microsoft.com/microsoft-edge/platform/issues/4365703/) for details.

≤12.1

3.1

4.4

18

4

≤12.1

2

1.0

## See also

- [Accessibility of keyboard-navigable JavaScript widgets](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Keyboard-navigable_JavaScript_widgets)
- The HTML `tabindex` global attribute.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/tabIndex" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/tabIndex</a>
