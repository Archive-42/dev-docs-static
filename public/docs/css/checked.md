# :checked

The `:checked` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) selector represents any **radio** (`<input type="radio">`), **checkbox** (`<input type="checkbox">`), or **option** ([`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) in a [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)) element that is checked or toggled to an `on` state.

    /* Matches any checked/selected radio, checkbox, or option */
    :checked {
      margin-left: 25px;
      border: 1px solid blue;
    }

The user can engage this state by checking/selecting an element, or disengage it by unchecking/deselecting the element.

**Note:** Because browsers often treat `<option>`s as [replaced elements](replaced_element), the extent to which they can be styled with the `:checked` pseudo-class varies from browser to browser.

## Syntax

    :checked

## Examples

### Basic example

#### HTML

    <div>
      <input type="radio" name="my-input" id="yes">
      <label for="yes">Yes</label>

      <input type="radio" name="my-input" id="no">
      <label for="no">No</label>
    </div>

    <div>
      <input type="checkbox" name="my-checkbox" id="opt-in">
      <label for="opt-in">Check me!</label>
    </div>

    <select name="my-select" id="fruit">
      <option value="opt1">Apples</option>
      <option value="opt2">Grapes</option>
      <option value="opt3">Pears</option>
    </select>

#### CSS

    div,
    select {
      margin: 8px;
    }

    /* Labels for checked inputs */
    input:checked + label {
      color: red;
    }

    /* Radio element, when checked */
    input[type="radio"]:checked {
      box-shadow: 0 0 0 3px orange;
    }

    /* Checkbox element, when checked */
    input[type="checkbox"]:checked {
      box-shadow: 0 0 0 3px hotpink;
    }

    /* Option elements, when selected */
    option:checked {
      box-shadow: 0 0 0 3px lime;
      color: red;
    }

#### Result

### Toggling elements with a hidden checkbox

This example utilizes the `:checked` pseudo-class to let the user toggle content based on the state of a checkbox, all without using [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript).

#### HTML

    <input type="checkbox" id="expand-toggle" />

    <table>
      <thead>
        <tr><th>Column #1</th><th>Column #2</th><th>Column #3</th></tr>
      </thead>
      <tbody>
        <tr class="expandable"><td>[more text]</td><td>[more text]</td><td>[more text]</td></tr>
        <tr><td>[cell text]</td><td>[cell text]</td><td>[cell text]</td></tr>
        <tr><td>[cell text]</td><td>[cell text]</td><td>[cell text]</td></tr>
        <tr class="expandable"><td>[more text]</td><td>[more text]</td><td>[more text]</td></tr>
        <tr class="expandable"><td>[more text]</td><td>[more text]</td><td>[more text]</td></tr>
      </tbody>
    </table>

    <label for="expand-toggle" id="expand-btn">Toggle hidden rows</label>

#### CSS

    /* Hide the toggle checkbox */
    #expand-toggle {
      display: none;
    }

    /* Hide expandable content by default */
    .expandable {
      visibility: collapse;
      background: #ddd;
    }

    /* Style the button */
    #expand-btn {
      display: inline-block;
      margin-top: 12px;
      padding: 5px 11px;
      background-color: #ff7;
      border: 1px solid;
      border-radius: 3px;
    }

    /* Show hidden content when the checkbox is checked */
    #expand-toggle:checked ~ * .expandable {
      visibility: visible;
    }

    /* Style the button when the checkbox is checked */
    #expand-toggle:checked ~ #expand-btn {
      background-color: #ccc;
    }

#### Result

### Image gallery

You can use the `:checked` pseudo-class to build an image gallery with full-size images that show only when the user clicks on a thumbnail. See <a href="https://developer.mozilla.org/@api/deki/files/6268/=css-checked-gallery.zip" class="internal">this demo</a> for a possible cue.

**Note:** For an analogous effect, but based on the <a href=":hover" class="internal"><code>:hover</code></a> pseudo-class and without hidden radioboxes, see <a href="https://developer.mozilla.org/@api/deki/files/6247/=css-gallery.zip" class="internal">this demo</a>, taken from the <a href=":hover" class="internal">:hover</a> reference page.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#selector-checked">HTML Living Standard<br />
<span class="small">The definition of ':checked' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/#selector-checked">HTML5<br />
<span class="small">The definition of ':checked' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines the semantic regarding HTML.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#checked">Selectors Level 4<br />
<span class="small">The definition of ':checked' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#checked">Selectors Level 3<br />
<span class="small">The definition of ':checked' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines the pseudo-class, but not the associated semantic</td></tr></tbody></table>

BCD tables only load in the browser

- [Web forms — working with user data](https://developer.mozilla.org/en-US/docs/Learn/Forms)
- [Styling web forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Styling_web_forms)
- Related HTML elements: `<input type="checkbox">`, `<input type="radio">`, [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), and [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option)
- [Replaced elements](replaced_element)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:checked" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:checked</a>
