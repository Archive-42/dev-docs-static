# HTMLSelectElement.selectedOptions

The **read-only** [`HTMLSelectElement`](../htmlselectelement) property `selectedOptions` contains a list of the [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) elements contained within the [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element that are currently selected. The list of selected options is an [`HTMLCollection`](../htmlcollection) object with one entry per currently selected option.

An option is considered selected if it has an <span class="page-not-created">`HTMLOptionElement.selected`</span> attribute.

## Syntax

    var selectedCollection = HTMLSelectElement.selectedOptions;

### Value

An [`HTMLCollection`](../htmlcollection) which lists every currently selected [`HTMLOptionElement`](../htmloptionelement) which is either a child of the [`HTMLSelectElement`](../htmlselectelement) or of an [`HTMLOptGroupElement`](../htmloptgroupelement) within the `<select>` element.

In other words, any option contained within the `<select>` element may be part of the results, but option groups are not included in the list.

If no options are currently selected, the collection is empty and returns a [`length`](../htmlcollection/length) of 0.

## Example

In this example, a [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element with a number of options is used to let the user order various food items.

### HTML

The HTML that creates the selection box and the [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) elements representing each of the food choices looks like this:

    <label for="foods">What do you want to eat?</label><br>
    <select id="foods" name="foods" size="7" multiple>
      <option value="1">Burrito</option>
      <option value="2">Cheeseburger</option>
      <option value="3">Double Bacon Burger Supreme</option>
      <option value="4">Pepperoni Pizza</option>
      <option value="5">Taco</option>
    </select>
    <br>
    <button name="order" id="order">
      Order Now
    </button>
    <p id="output">
    </p>

The `<select>` element is set to allow multiple items to be selected, and it is 7 rows tall. Note also the [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button), whose role it is to trigger fetching the [`HTMLCollection`](../htmlcollection) of selected elements using the `selected` property.

### JavaScript

The JavaScript code that establishes the event handler for the button, as well as the event handler itself, looks like this:

    let orderButton = document.getElementById("order");
    let itemList = document.getElementById("foods");
    let outputBox = document.getElementById("output");

    orderButton.addEventListener("click", function() {
      let collection = itemList.selectedOptions;
      let output = "";

      for (let i=0; i<collection.length; i++) {
        if (output === "") {
          output = "Your order for the following items has been placed: ";
        }
        output += collection[i].label;

        if (i === (collection.length - 2) && (collection.length < 3)) {
          output +=  " and ";
        } else if (i < (collection.length - 2)) {
          output += ", ";
        } else if (i === (collection.length - 2)) {
          output += ", and ";
        }
      }

      if (output === "") {
        output = "You didn't order anything!";
      }

      outputBox.innerHTML = output;
    }, false);

This script sets up a `click` event listener on the "Order Now" button. When clicked, the event handler fetches the list of selected options using `selectedOptions`, then iterates over the options in the list. A string is constructed to list the ordered items, with logic to build the list using proper English grammar rules (including a [serial comma](https://en.wikipedia.org/wiki/Serial_comma)).

### Result

The resulting content looks like this in action:

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/form-elements.html#dom-select-selectedoptions">HTML Living Standard<br />
<span class="small">The definition of 'HTMLSelectElement.selectedOptions' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#dom-select-selectedoptions">HTML5<br />
<span class="small">The definition of 'HTMLSelectElement.selectedOptions' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`selectedOptions`

19

12

26

No

9

6

≤37

25

26

10.1

6

1.5

## See also

- [Drop-down controls](https://developer.mozilla.org/en-US/docs/Learn/Forms/Other_form_controls#drop-down_controls) in [Other form controls](https://developer.mozilla.org/en-US/docs/Learn/Forms/Other_form_controls)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/selectedOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/selectedOptions</a>
