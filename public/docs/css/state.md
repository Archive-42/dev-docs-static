# :state()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `:state` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents any [custom element](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements) with the specified custom state in <span class="page-not-created">`ElementInternals.states`</span>.

    custom-element:state(foo) {
      /* Styles to apply when `custom-element` is in the `foo` state */
    }

## Syntax

{{CSSSyntax}}

## Examples

Fill in a simple example that nicely shows a typical usage of the selector, then perhaps some more complex examples (see our guide on how to add [code examples](https://developer.mozilla.org/en-US/docs/MDN/Structures/Code_examples) for more information).

    my code block

And/or include a list of links to useful code samples that live elsewhere:

- x
- y
- z

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="about:unknown#selectordef-state">Unknown<br />
<span class="small">The definition of 'The <code>:state()</code> selector' in that specification.</span></a></td><td><span class="spec-">Unknown</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `css.selectors.state`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- The <span class="page-not-created">`ElementInternals.states`</span> property - [`DOMTokenList`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList) used to configure which custom states a custom element is in.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:state" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:state</a>
