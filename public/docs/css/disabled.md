# :disabled

The `:disabled` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents any disabled element. An element is disabled if it can't be activated (selected, clicked on, typed into, etc.) or accept focus. The element also has an enabled state, in which it can be activated or accept focus.

    /* Selects any disabled <input> */
    input:disabled {
      background: #ccc;
    }

## Syntax

    :disabled

## Examples

This example shows a basic shipping form. It uses the [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) `change` event to let the user enable/disable the billing fields.

### HTML

    <form action="#">
      <fieldset id="shipping">
        <legend>Shipping address</legend>
        <input type="text" placeholder="Name">
        <input type="text" placeholder="Address">
        <input type="text" placeholder="Zip Code">
      </fieldset>
      <br>
      <fieldset id="billing">
        <legend>Billing address</legend>
        <label for="billing-checkbox">Same as shipping address:</label>
        <input type="checkbox" id="billing-checkbox" checked>
        <br>
        <input type="text" placeholder="Name" disabled>
        <input type="text" placeholder="Address" disabled>
        <input type="text" placeholder="Zip Code" disabled>
      </fieldset>
    </form>

### CSS

    input[type="text"]:disabled {
      background: #ccc;
    }

### JavaScript

    // Wait for the page to finish loading
    document.addEventListener('DOMContentLoaded', function () {
      // Attach `change` event listener to checkbox
      document.getElementById('billing-checkbox').onchange = toggleBilling;
    }, false);

    function toggleBilling() {
      // Select the billing text fields
      var billingItems = document.querySelectorAll('#billing input[type="text"]');

      // Toggle the billing text fields
      for (var i = 0; i < billingItems.length; i++) {
        billingItems[i].disabled = !billingItems[i].disabled;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#selector-disabled">HTML Living Standard<br />
<span class="small">The definition of ':disabled' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/#selector-disabled">HTML5<br />
<span class="small">The definition of ':disabled' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines the semantics of HTML and forms.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#enableddisabled">Selectors Level 4<br />
<span class="small">The definition of ':disabled' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#enableddisabled">Selectors Level 3<br />
<span class="small">The definition of ':disabled' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines the pseudo-class, but not the associated semantics.</td></tr></tbody></table>

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

`:disabled`

1

12

Edge does not recognize `:disabled` on the [`<fieldset>`](https://developer.mozilla.org/docs/Web/HTML/Element/fieldset) element.

1

9

Internet Explorer does not recognize `:disabled` on the [`<fieldset>`](https://developer.mozilla.org/docs/Web/HTML/Element/fieldset) element.

9

3.1

2

18

4

10.1

3.1

1.0

## See also

- [`:enabled`](:enabled)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:disabled" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:disabled</a>
