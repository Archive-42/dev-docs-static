# Element.ariaMultiline

### Note

The `ariaMultiline` property of the [`Element`](../element) interface reflects the value of the `aria-multiline` attribute, which indicates whether a text box accepts multiple lines of input or only a single line.

Where possible use an HTML [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element with `type="text"` or a [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) as these have built in semantics and do not require ARIA attributes.

## Syntax

    var ariaMultiline = element.ariaMultiline;
    element.ariaMultiline = ariaMultiline

### Value

A [`DOMString`](../domstring) with one of the following values:

`"true"`  
This is a multi-line text box.

`"false"`  
This is a single-line text box.

## Examples

In this example the `aria-multiline` attribute on the element with an ID of `txtBoxInput` is set to "true" indicating that this box allows for multiple lines of input. Using `ariaPlaceholder` we update the value to "false".

    <div id="txtboxMultilineLabel">Enter the tags for the article</div>
    <div role="textbox" id="txtBoxInput" contenteditable="true" aria-multiline="true"
      aria-labelledby="txtboxMultilineLabel" aria-required="true"></div>

    let el = document.getElementById('txtBoxInput');
    console.log(el.ariaMultiline); // "true"
    el.ariaMultiline = "false"
    console.log(el.ariaMultiline); // "false"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariamultiline">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaMultiline' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.Element.ariaMultiline`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [ARIA: textbox role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/textbox_role)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaMultiline" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaMultiline</a>
