# :placeholder-shown

The `:placeholder-shown` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents any [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element that is currently displaying [placeholder text](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-placeholder).

    /* Selects any element with an active placeholder */
    :placeholder-shown {
      border: 2px solid silver;
    }

## Syntax

    :placeholder-shown

## Examples

### Basic example

This example applies special font and border styles when the placeholder is shown.

#### HTML

    <input placeholder="Type something here!">

#### CSS

    input {
      border: 1px solid black;
      padding: 3px;
    }

    input:placeholder-shown {
      border-color: teal;
      color: purple;
      font-style: italic;
    }

#### Result

### Overflowing text

When form fields are too small, placeholder text can get cropped in an undesirable way. You can use the [`text-overflow`](text-overflow) property to alter the way overflowing text is displayed.

#### HTML

    <input id="input1" placeholder="Name, Rank, and Serial Number">
    <br><br>
    <input id="input2" placeholder="Name, Rank, and Serial Number">

#### CSS

    #input2:placeholder-shown {
      text-overflow: ellipsis;
    }

#### Result

### Customized input field

The following example highlights the Branch and ID code fields with a custom style.

#### HTML

    <form id="test">
      <p>
        <label for="name">Enter Student Name:</label>
        <input id="name" placeholder="Student Name"/>
      </p>
      <p>
        <label for="branch">Enter Student Branch:</label>
        <input id="branch" placeholder="Student Branch"/>
      </p>
      <p>
        <label for="sid">Enter Student ID:</label>
        <input type="number" pattern="[0-9]{8}" title="8 digit ID" id="sid" class="studentid" placeholder="8 digit id"/>
      </p>
      <input type="submit"/>
    </form>

#### CSS

    input {
      background-color: #E8E8E8;
      color: black;
    }

    input.studentid:placeholder-shown {
      background-color: yellow;
      color: red;
      font-style: italic;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#placeholder">Selectors Level 4<br />
<span class="small">The definition of ':placeholder-shown' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:placeholder-shown`

47

79

51

4-51

10

34

9

47

47

51

4-51

34

9

5.0

`non_text_types`

47

79

59

No

34

9

47

47

59

34

9

5.0

## See also

- The [`::placeholder`](::placeholder) pseudo-element styles the placeholder _itself_.
- Related HTML elements: [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)
- [HTML forms](https://developer.mozilla.org/en-US/docs/Learn/Forms)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:placeholder-shown" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:placeholder-shown</a>
