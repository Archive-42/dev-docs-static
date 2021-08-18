# Element.ariaExpanded

The `ariaExpanded` property of the [`Element`](../element) interface reflects the value of the `aria-expanded` attribute, which indicates whether a grouping element owned or controlled by this element is expanded or collapsed.

## Syntax

    var ariaExpanded = element.ariaExpanded;
    element.ariaExpanded = ariaExpanded

### Value

A [`DOMString`](../domstring) with one of the following values:

`"true"`  
The grouping element this element owns or controls is expanded.

`"false"`  
The grouping element this element owns or controls is collapsed.

`"undefined"`  
The element does not own or control a grouping element that is expandable.

## Examples

In this example the `aria-expanded` attribute on the element with an ID of `animal` is set to "false". Using `ariaExpanded` we update the value to "true".

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
    console.log(el.ariaExpanded); // false
    el.ariaExpanded = "true";
    console.log(el.ariaExpanded); // true

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariaexpanded">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaExpanded' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaExpanded`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaExpanded" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaExpanded</a>
