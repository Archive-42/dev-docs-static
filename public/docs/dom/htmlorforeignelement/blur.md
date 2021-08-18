# HTMLElement.blur()

The `HTMLElement.blur()` method removes keyboard focus from the current element.

## Syntax

    element.blur();

## Examples

### Remove focus from a text input

#### HTML

    <input type="text" id="myText" value="Sample Text">
    <br><br>
    <button type="button" onclick="focusInput()">Click me to gain focus</button>
    <button type="button" onclick="blurInput()">Click me to lose focus</button>

#### JavaScript

    function focusInput() {
      document.getElementById('myText').focus();
    }
    function blurInput() {
      document.getElementById('myText').blur();
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/editing.html#dom-blur">HTML Living Standard<br />
<span class="small">The definition of 'blur' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#blur()-0">HTML 5.1<br />
<span class="small">The definition of 'blur' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/editing.html#dom-blur">HTML5<br />
<span class="small">The definition of 'blur' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-28216144">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'blur' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr></tbody></table>

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

`blur`

1

12

1.5

5.5

8

3

4.4

18

4

10.1

1

1.0

## See also

- DOM method [`HTMLOrForeignElement.focus`](focus)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/blur" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/blur</a>
