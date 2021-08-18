# :default

The `:default` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) selects form elements that are the default in a group of related elements.

What this selector matches is defined in [HTML Standard §4.16.3 Pseudo-classes](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-default) — it may match the [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button), `<input type="checkbox">`, `<input type="radio">`, and [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) elements:

- A default option element is the first one with the `selected` attribute, or the first enabled option in DOM order. `multiple` [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)s can have more than one `selected` option, so all will match `:default`.
- `<input type="checkbox">` and `<input type="radio">` match if they have the `checked` attribute.
- [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) matches if it is a [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)’s [default submission button](https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#implicit-submission): the first `<button>` in DOM order that belongs to the form. This also applies to [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) types that submit forms, like `image` or `submit`.

## Syntax

    :default

## Examples

### HTML

    <fieldset>
      <legend>Favorite season</legend>

      <input type="radio" name="season" id="spring">
      <label for="spring">Spring</label>

      <input type="radio" name="season" id="summer" checked>
      <label for="summer">Summer</label>

      <input type="radio" name="season" id="fall">
      <label for="fall">Fall</label>

      <input type="radio" name="season" id="winter">
      <label for="winter">Winter</label>
    </fieldset>

### CSS

    input:default {
      box-shadow: 0 0 2px 1px coral;
    }

    input:default + label {
      color: coral;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#selector-default">HTML Living Standard<br />
<span class="small">The definition of ':default' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/#selector-default">HTML5<br />
<span class="small">The definition of ':default' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines associated HTML semantics and constraint validation.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#default-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':default' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change.</td></tr></tbody></table>

BCD tables only load in the browser

- [Web forms — Working with user data](https://developer.mozilla.org/en-US/docs/Learn/Forms)
- [Styling web forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Styling_web_forms)
- Related HTML elements: [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button), `<input type="checkbox">`, `<input type="radio">`, and [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:default" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:default</a>
