# Element.ariaAutoComplete

The `ariaAutoComplete` property of the [`Element`](../element) interface reflects the value of the `aria-autocomplete` attribute, which indicates whether inputting text could trigger display of one or more predictions of the user's intended value for a combobox, searchbox, or textbox and specifies how predictions would be presented if they were made.

## Syntax

    var ariaAutoComplete = element.ariaAutoComplete;
    element.ariaAutoComplete = ariaAutoComplete

### Value

A [`DOMString`](../domstring) with one of the following values:

`"inline"`  
When a user is providing input, text suggesting one way to complete the provided input may be dynamically inserted after the caret.

`"list"`  
When a user is providing input, an element containing a collection of values that could complete the provided input may be displayed.

`"both"`  
When a user is providing input, an element containing a collection of values that could complete the provided input may be displayed. If displayed, one value in the collection is automatically selected, and the text needed to complete the automatically selected value appears after the caret in the input.

`"none"`  
When a user is providing input, there is no display of an automatic suggestion that attempts to predict how the user intends to complete the input.

## Examples

In this example the `aria-autocomplete` attribute on the element with an ID of `animal` is set to "list". Using `ariaAutoComplete` we update the value to "inline".

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
    console.log(el.ariaAutoComplete); // list
    el.ariaAutoComplete = "inline";
    console.log(el.ariaAutoComplete); // inline

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariaautocomplete">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaAutoComplete' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaAutoComplete`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaAutoComplete" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaAutoComplete</a>
