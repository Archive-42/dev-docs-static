# ::file-selector-button

The `::file-selector-button` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-element](pseudo-elements) represents the button of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) of `type="file"`.

WebKit/Blink compatible browsers like Chrome, Opera and Safari (indicated by the `-webkit` prefix) support a non-standard pseudo-class `::-webkit-file-upload-button` which serves the same purpose.

## Syntax

    selector::file-selector-button

## Examples

### HTML

    <form>
      <label for="fileUpload">Upload file</label>
      <input type="file" id="fileUpload">
    </form>

### CSS

    input[type=file]::file-selector-button {
      border: 2px solid #6c5ce7;
      padding: .2em .4em;
      border-radius: .2em;
      background-color: #a29bfe;
      transition: 1s;
    }

    input[type=file]::file-selector-button:hover {
      background-color: #81ecec;
      border: 2px solid #00cec9;
    }

Example with fallback for browsers supporting the `-webkit` prefix. Note that as a selector you will need to write out the whole code block twice, as an unrecognized selector invalidates the whole list.

Note that `::file-selector-button` is a whole element, and as such matches the rules from the UA stylesheet. In particular, fonts and colors won't necessarily inherit from the `input` element.

### HTML

    <form>
      <label for="fileUpload">Upload file</label>
      <input type="file" id="fileUpload">
    </form>

### CSS

    input[type=file]::-webkit-file-upload-button {
      border: 2px solid #6c5ce7;
      padding: .2em .4em;
      border-radius: .2em;
      background-color: #a29bfe;
      transition: 1s;
    }

    input[type=file]::file-selector-button {
      border: 2px solid #6c5ce7;
      padding: .2em .4em;
      border-radius: .2em;
      background-color: #a29bfe;
      transition: 1s;
    }

    input[type=file]::-webkit-file-upload-button:hover {
      background-color: #81ecec;
      border: 2px solid #00cec9;
    }

    input[type=file]::file-selector-button:hover {
      background-color: #81ecec;
      border: 2px solid #00cec9;
    }

## Specifications

The pseudo-element [has been resolved on by the CSS WG](https://github.com/w3c/csswg-drafts/issues/5049#issuecomment-666449792) however the edit has not yet been made in a specification.

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

`::file-selector-button`

89

1

89

79

82

No

75

15

No

3

89

1

89

18

82

No

14

No

1

No

1.0

## See also

- [WebKit CSS extensions](https://developer.mozilla.org/en-US/docs/Web/CSS/WebKit_Extensions)
- [File and Directory Entries API](https://developer.mozilla.org/en-US/docs/Web/API/File_and_Directory_Entries_API)
- [File and Directory Entries API support in Firefox](https://developer.mozilla.org/en-US/docs/Web/API/File_and_Directory_Entries_API/Firefox_support)
- `<input type="file">`

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/::file-selector-button" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/::file-selector-button</a>
