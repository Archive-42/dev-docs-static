# Element.ariaHasPopup

The `ariaHasPopup` property of the [`Element`](../element) interface reflects the value of the `aria-haspopup` attribute, which indicates the availability and type of interactive popup element, such as menu or dialog, that can be triggered by an element.

## Syntax

    var ariaHasPopup = element.ariaHasPopup;
    element.ariaHasPopup = ariaHasPopup

### Value

A [`DOMString`](../domstring) with one of the following values:

`"false"`  
The element does not have a popup.

`"true"`  
The element has a popup that is a menu.

`"menu"`  
The element has a popup that is a menu.

`"listbox"`  
The element has a popup that is a listbox.

`"tree"`  
The element has a popup that is a tree.

`"grid"`  
The element has a popup that is a grid.

`"dialog"`  
The element has a popup that is a dialog.

## Examples

In this example the `aria-haspopup` attribute on the element with an ID of `animal` is set to "true". Using `ariaHasPopup` we update the value to "false".

    <div class="animals-combobox">
      <label for="animal">Animal</label>
      <input id="animal" type="text" role="combobox" aria-autocomplete="list" aria-expanded="false" aria-haspopup="true">
      <button id="animals-button" tabindex="-1" aria-label="Open">▽</button>
      <ul id="animals-listbox" role="listbox" aria-label="Animals">
        <li id="animal-cat" role="option">Cat</li>
        <li id="animal-dog" role="option">Dog</li>
      </ul>
    </div>

    let el = document.getElementById('animal');
    console.log(el.ariaHasPopup); // true
    el.ariaHasPopup = "false";
    console.log(el.ariaHasPopup); // false

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariahaspopup">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaHasPopup' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaHasPopup`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaHasPopup" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaHasPopup</a>
