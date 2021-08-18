# Element.ariaKeyShortcuts

The `ariaKeyShortcuts` property of the [`Element`](../element) interface reflects the value of the `aria-keyshortcuts` attribute, which indicates keyboard shortcuts that an author has implemented to activate or give focus to an element.

## Syntax

    var ariaKeyShortcuts = element.ariaKeyShortcuts;
    element.ariaKeyShortcuts = ariaKeyShortcuts

### Value

A [`DOMString`](../domstring).

## Examples

In this example the `aria-keyshortcuts` attribute on the element with an ID of `skip-link` is set to "Alt+Shift+A". Using `ariaKeyShortcuts` we update the value to "Alt+Shift+M".

    <a id="skip-link" href="#content" aria-keyshortcuts="Alt+Shift+A">Skip to content</a>

    let el = document.getElementById('saveChanges');
    console.log(el.ariaKeyShortcuts); // "Alt+Shift+A"
    el.ariaKeyShortcuts = "Alt+Shift+M"
    console.log(el.ariaKeyShortcuts); // "Alt+Shift+M"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariakeyshortcuts">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaKeyShortcuts' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaKeyShortcuts`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaKeyShortcuts" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaKeyShortcuts</a>
