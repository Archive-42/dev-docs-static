# Element.ariaMultiSelectable

### Note

The `ariaMultiSelectable` property of the [`Element`](../element) interface reflects the value of the `aria-multiselectable` attribute, which indicates that the user may select more than one item from the current selectable descendants.

Where possible use an HTML [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element as this has built in semantics and does not require ARIA attributes.

## Syntax

    var ariaMultiSelectable = element.ariaMultiSelectable;
    element.ariaMultiSelectable = ariaMultiSelectable

### Value

A [`DOMString`](../domstring) with one of the following values:

`"true"`  
More than one item may be selected at a time.

`"false"`  
Only one item may be selected.

## Examples

In this example the `aria-multiselectable` attribute on the element with an ID of `listbox1` is set to "true" indicating that this input accepts multiple selected items. Using `ariaMultiSelectable` we update the value to "false".

    <div role="listbox" tabindex="0" id="listbox1"
      aria-multiselectable="true" aria-labelledby="listbox1label" aria-activedescendant="listbox1-1">
      <div role="option" id="listbox1-1" class="selected" aria-selected="true">Green</div>
      <div role="option" id="listbox1-2">Orange</div>
      <div role="option" id="listbox1-3">Red</div<
    </div>

    let el = document.getElementById('listbox1');
    console.log(el.ariaMultiSelectable); // "true"
    el.ariaMultiSelectable = "false"
    console.log(el.ariaMultiSelectable); // "false"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariamultiselectable">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaMultiSelectable' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaMultiSelectable`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

## See also

- [ARIA: listbox role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/listbox_role)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaMultiSelectable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaMultiSelectable</a>
