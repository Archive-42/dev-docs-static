# HTMLTextAreaElement

The `HTMLTextAreaElement` interface provides special properties and methods for manipulating the layout and presentation of [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) elements.

## Properties

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><code>accessKey</code></td><td><code>string:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-accesskey"><code>accesskey</code></a> attribute.</td></tr><tr class="even"><td><code>autocapitalize</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td><code>string:</code> Returns / Sets the element's capitalization behavior for user input. Valid values are: <code>none</code>, <code>off</code>, <code>characters</code>, <code>words</code>, <code>sentences</code>.</td></tr><tr class="odd"><td><code>autocomplete</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td></td></tr><tr class="even"><td><code>autofocus</code></td><td><code>boolean:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-autofocus"><code>autofocus</code></a> attribute, indicating that the control should have input focus when the page loads</td></tr><tr class="odd"><td><code>cols</code></td><td><code>unsigned long:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-cols"><code>cols</code></a> attribute, indicating the visible width of the text area.</td></tr><tr class="even"><td><code>defaultValue</code></td><td><code>string:</code> Returns / Sets the control's default value, which behaves like the <a href="node/textcontent"><code>Node.textContent</code></a> property.</td></tr><tr class="odd"><td><code>disabled</code></td><td><code>boolean:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-disabled"><code>disabled</code></a> attribute, indicating that the control is not available for interaction.</td></tr><tr class="even"><td><code>form</code> <span class="badge inline readonly">Read only </span></td><td><code>object:</code> Returns a reference to the parent form element. If this element is not contained in a form element, it can be the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-id"><code>id</code></a> attribute of any <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form"><code>&lt;form&gt;</code></a> element in the same document or the value <code>null</code>.</td></tr><tr class="odd"><td><code>inputMode</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td></td></tr><tr class="even"><td><code>maxLength</code></td><td><code>long:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-maxlength"><code>maxlength</code></a> attribute, indicating the maximum number of characters the user can enter. This constraint is evaluated only when the value changes.</td></tr><tr class="odd"><td><code>minLength</code></td><td><code>long:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-minlength"><code>minlength</code></a> attribute, indicating the minimum number of characters the user can enter. This constraint is evaluated only when the value changes.</td></tr><tr class="even"><td><code>name</code></td><td><code>string:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-name"><code>name</code></a> attribute, containing the name of the control.</td></tr><tr class="odd"><td><code>placeholder</code></td><td><code>string:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-placeholder"><code>placeholder</code></a> attribute, containing a hint to the user about what to enter in the control.</td></tr><tr class="even"><td><code>readOnly</code></td><td><code>boolean:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-readonly"><code>readonly</code></a> attribute, indicating that the user cannot modify the value of the control.</td></tr><tr class="odd"><td><code>required</code></td><td><code>boolean:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-required"><code>required</code></a> attribute, indicating that the user must specify a value before submitting the form.</td></tr><tr class="even"><td><code>rows</code></td><td><code>unsigned long:</code> Returns / Sets the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-rows"><code>rows</code></a> attribute, indicating the number of visible text lines for the control.</td></tr><tr class="odd"><td><code>selectionDirection</code></td><td><code>string:</code> Returns / Sets the direction in which selection occurred. This is "<code>forward</code>" if selection was performed in the start-to-end direction of the current locale, or "<code>backward</code>" for the opposite direction. This can also be "<code>none</code>" if the direction is unknown.</td></tr><tr class="even"><td><code>selectionEnd</code></td><td><code>unsigned long:</code> Returns / Sets the index of the end of selected text. If no text is selected, contains the index of the character that follows the input cursor. On being set, the control behaves as if <code>setSelectionRange()</code> had been called with this as the second argument, and <code>selectionStart</code> as the first argument.</td></tr><tr class="odd"><td><code>selectionStart</code></td><td><code>unsigned long:</code> Returns / Sets the index of the beginning of selected text. If no text is selected, contains the index of the character that follows the input cursor. On being set, the control behaves as if <code>setSelectionRange()</code> had been called with this as the first argument, and <code>selectionEnd</code> as the second argument.</td></tr><tr class="even"><td><code>tabIndex</code></td><td><code>long:</code> Returns / Sets the position of the element in the tabbing navigation order for the current document.</td></tr><tr class="odd"><td><code>textLength</code> <span class="badge inline readonly">Read only </span></td><td><code>long:</code> Returns the codepoint length of the control's <code>value</code>. Same as reading <code>value.length</code></td></tr><tr class="even"><td><code>type</code> <span class="badge inline readonly">Read only </span></td><td><code>string:</code> Returns the string <code>textarea</code>.</td></tr><tr class="odd"><td><code>validationMessage</code> <span class="badge inline readonly">Read only </span></td><td><code>string:</code> Returns a localized message that describes the validation constraints that the control does not satisfy (if any). This is the empty string if the control is not a candidate for constraint validation (<code>willValidate</code> is <code>false</code>), or it satisfies its constraints.</td></tr><tr class="even"><td><code>validity</code> <span class="badge inline readonly">Read only </span></td><td><code>ValidityState</code> object: Returns the validity states that this element is in.</td></tr><tr class="odd"><td><code>value</code></td><td><code>string:</code> Returns / Sets the raw value contained in the control.</td></tr><tr class="even"><td><code>willValidate</code> <span class="badge inline readonly">Read only </span></td><td><p><code>boolean:</code> Returns whether the element is a candidate for constraint validation. <code>false</code> if any conditions bar it from constraint validation, including its <code>readOnly</code> or <code>disabled</code> property is <code>true</code>.</p></td></tr><tr class="odd"><td><code>wrap</code></td><td><code>string:</code> Returns / Sets the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea#attr-wrap"><code>wrap</code></a> HTML attribute, indicating how the control wraps text.</td></tr><tr class="even"><td><a href="htmltextareaelement/labels"><code>HTMLTextAreaElement.labels</code></a><span class="badge inline readonly">Read only </span></td><td><a href="nodelist"><code>NodeList</code></a>: Returns a list of label elements associated with this element.</td></tr></tbody></table>

The two properties `tabIndex` and `accessKey` are inherited from [`HTMLElement`](htmlelement) from HTML5 on, but were defined on `HTMLTextAreaElement` in DOM Level 2 HTML and earlier specifications.

## Methods

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="htmlorforeignelement/blur"><code>blur()</code></a></td><td>Removes focus from the control; keystrokes will subsequently go nowhere.</td></tr><tr class="even"><td><a href="htmlorforeignelement/focus"><code>focus()</code></a></td><td>Gives focus to the control; keystrokes will subsequently go to this element.</td></tr><tr class="odd"><td><a href="htmlinputelement/select"><code>select()</code></a></td><td>Selects the contents of the control.</td></tr><tr class="even"><td><a href="htmlinputelement/setrangetext"><code>setRangeText()</code></a></td><td>Replaces a range of text in the element with new text.</td></tr><tr class="odd"><td><a href="htmlinputelement/setselectionrange"><code>setSelectionRange()</code></a></td><td>Selects a range of text in the element (but does not focus it).</td></tr><tr class="even"><td><code>checkValidity()</code></td><td>Returns <code>false</code> if the element is a candidate for constraint validation, and it does not satisfy its constraints. In this case, it also fires a cancelable <code>invalid</code> event at the control. It returns <code>true</code> if the control is not a candidate for constraint validation, or if it satisfies its constraints.</td></tr><tr class="odd"><td><code>reportValidity()</code></td><td><p>This method reports the problems with the constraints on the element, if any, to the user. If there are problems, it fires a cancelable <code>invalid</code> event at the element, and returns <code>false</code>; if there are no problems, it returns <code>true</code>.</p></td></tr><tr class="even"><td><code>setCustomValidity(DOMstring)</code></td><td>Sets a custom validity message for the element. If this message is not the empty string, then the element is suffering from a custom validity error, and does not validate.</td></tr></tbody></table>

The two methods `blur()` and `focus()` are inherited from [`HTMLElement`](htmlelement) from HTML5 on, but were defined on `HTMLTextAreaElement` in DOM Level 2 HTML and earlier specifications.

## Events

Listen to these events using [`addEventListener()`](eventtarget/addeventlistener) or by assigning an event listener to the `oneventname` property of this interface:

[`input`](htmlelement/input_event) event  
Fires when the `value` of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element has been changed.

## Examples

### Autogrowing textarea example

Make a textarea autogrow while typing:

#### JavaScript

    function autoGrow (oField) {
      if (oField.scrollHeight > oField.clientHeight) {
        oField.style.height = oField.scrollHeight + "px";
      }
    }

#### CSS

    textarea.noscrollbars {
      overflow: hidden;
      width: 300px;
      height: 100px;
    }

#### HTML

    <form>
      <fieldset>
        <legend>Your comments</legend>
        <p><textarea class="noscrollbars" onkeyup="autoGrow(this);"></textarea></p>
        <p><input type="submit" value="Send" /></p>
      </fieldset>
    </form>

### Insert HTML tags example

Insert some HTML tags or _smiles_ or any custom text in a textarea.

#### JavaScript

    function insertMetachars(sStartTag, sEndTag) {
      var bDouble = arguments.length > 1, oMsgInput = document.myForm.myTxtArea, nSelStart = oMsgInput.selectionStart, nSelEnd = oMsgInput.selectionEnd, sOldText = oMsgInput.value;
      oMsgInput.value = sOldText.substring(0, nSelStart) + (bDouble ? sStartTag + sOldText.substring(nSelStart, nSelEnd) + sEndTag : sStartTag) + sOldText.substring(nSelEnd);
      oMsgInput.setSelectionRange(bDouble || nSelStart === nSelEnd ? nSelStart + sStartTag.length : nSelStart, (bDouble ? nSelEnd : nSelStart) + sStartTag.length);
      oMsgInput.focus();
    }

#### CSS

CSS to decorate the internal span to behave like a link:

    .intLink {
      cursor: pointer;
      text-decoration: underline;
      color: #0000ff;
    }

HTML:

    <form name="myForm">
    <p>[&nbsp;<span class="intLink" onclick="insertMetachars('&lt;strong&gt;','&lt;\/strong&gt;');"><strong>Bold</strong></span> | <span class="intLink" onclick="insertMetachars('&lt;em&gt;','&lt;\/em&gt;');"><em>Italic</em></span> | <span class="intLink" onclick="var newURL=prompt('Enter the full URL for the link');if(newURL){insertMetachars('&lt;a href=\u0022'+newURL+'\u0022&gt;','&lt;\/a&gt;');}else{document.myForm.myTxtArea.focus();}">URL</span> | <span class="intLink" onclick="insertMetachars('\n&lt;code&gt;\n','\n&lt;\/code&gt;\n');">code</span> | <span class="intLink" onclick="insertMetachars(' :-)');">smile</span> | etc. etc.&nbsp;]</p>
    <p><textarea name="myTxtArea" rows="10" cols="50">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut facilisis, arcu vitae adipiscing placerat, nisl lectus accumsan nisi, vitae iaculis sem neque vel lectus. Praesent tristique commodo lorem quis fringilla. Sed ac tellus eros. Sed consectetur eleifend felis vitae luctus. Praesent sagittis, est eget bibendum tincidunt, ligula diam tincidunt augue, a fermentum odio velit eget mi. Phasellus mattis, elit id fringilla semper, orci magna cursus ligula, non venenatis lacus augue sit amet dui. Pellentesque lacinia odio id nisi pulvinar commodo tempus at odio. Ut consectetur eros porttitor nunc mollis ultrices. Aenean porttitor, purus sollicitudin viverra auctor, neque erat blandit sapien, sit amet tincidunt massa mi ac nibh. Proin nibh sem, bibendum ut placerat nec, cursus et lacus. Phasellus vel augue turpis. Nunc eu mauris eu leo blandit mollis interdum eget lorem. </textarea></p>
    </form>

### Maximum length and number of lines example

Create a textarea with a maximum number of characters per line and a maximum number of lines:

First, create a function that takes the text field and a key event as input and determines if any of the limits have been reached. If the limit has not been reached, it will return the key.

    function checkRows(oField, oKeyEvent) {
      var nKey = (oKeyEvent || /* old IE */ window.event || /* check is not supported! */ { keyCode: 38 }).keyCode,

        // put here the maximum number of characters per line:
        nCols = 30,
        // put here the maximum number of lines:
        nRows = 5,

        nSelS = oField.selectionStart, nSelE = oField.selectionEnd,
        sVal = oField.value, nLen = sVal.length,

        nBackward = nSelS >= nCols ? nSelS - nCols : 0,
        nDeltaForw = sVal.substring(nBackward, nSelS).search(new RegExp("\\n(?!.{0," + String(nCols - 2) + "}\\n)")) + 1,
        nRowStart = nBackward + nDeltaForw,
        aReturns = (sVal.substring(0, nSelS) + sVal.substring(nSelE, sVal.length)).match(/\n/g),
        nRowEnd = nSelE + nRowStart + nCols - nSelS,
        sRow = sVal.substring(nRowStart, nSelS) + sVal.substring(nSelE, nRowEnd > nLen ? nLen : nRowEnd),
        bKeepCols = nKey === 13 || nLen + 1 < nCols || /\n/.test(sRow) || ((nRowStart === 0 || nDeltaForw > 0 || nKey > 0) && (sRow.length < nCols || (nKey > 0 && (nLen === nRowEnd || sVal.charAt(nRowEnd) === "\n"))));

      return (nKey !== 13 || (aReturns ? aReturns.length + 1 : 1) < nRows) && ((nKey > 32 && nKey < 41) || bKeepCols);
    }

In the HTML we just need to hook our function to the \`onkeypress\` event and specify that our textarea does not accept pasting:

    <form>
      <p>Textarea with fixed number of characters per line:<br />
        <textarea cols="50" rows="10" onkeypress="return checkRows(this, event);"
                  onpaste="return false;"></textarea>
      </p>
    </form>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmltextareaelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTextAreaElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#the-textarea-element">HTML5<br />
<span class="small">The definition of 'HTMLTextAreaElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The attributes <code>tabindex</code> and <code>accesskey</code>, as well as the methods <code>blur()</code> and <code>focus()</code> are now defined on <a href="htmlelement"><code>HTMLElement</code></a>.<br />
The following attributes have been added: <code>autofocus</code>, <code>placeholder</code>, <code>dirName</code>, <code>wrap</code>, <code>maxLength</code>, <code>required</code>, <code>textLength</code>, <code>labels</code>, <code>selectionStart</code>, <code>selectionEnd</code>, <code>selectionDirection</code>, <code>validity</code>, <code>validationMessage</code>, and <code>willValidate</code>.<br />
The following methods have been added: <code>checkValidity()</code>, <code>setCustomValidity()</code>, and <code>setSelectionRange()</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-ID-24874179">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLTextAreaElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>The property <code>defaultValue</code> doesn't contain the initial value of the <code>value</code> attribute, but the initial value of the content of the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea"><code>&lt;textarea&gt;</code></a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-24874179">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLTextAreaElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`HTMLTextAreaElement`

1

12

1

5

8

1

1

18

4

10.1

1

1.0

`autocapitalize`

43

79

No

No

?

No

No

43

No

?

≤3

4.0

`autocomplete`

66

79

59

No

53

9

66

66

59

47

9

9.0

`checkValidity`

4

12

4

10

≤12.1

5

≤37

18

4

≤12.1

5

1.0

`cols`

1

12

1

5

≤12.1

1

1

18

4

≤12.1

1

1.0

`defaultValue`

1

12

1

5

≤12.1

1

1

18

4

≤12.1

1

1.0

`dirName`

17

79

No

No

≤12.1

6

≤37

18

No

≤12.1

6

1.0

`disabled`

1

12

1

5

≤12.1

1

1

18

4

≤12.1

1

1.0

`form`

1

12

1

5

≤12.1

1

1

18

4

≤12.1

1

1.0

`labels`

6

18

56

No

≤12.1

5.1

≤37

18

56

≤12.1

5

1.0

`maxLength`

4

12

4

10

≤12.1

5

≤37

18

4

≤12.1

5

1.0

`minLength`

40

17

51

No

27

10.1

40

40

51

27

10.3

4.0

`name`

1

12

1

5

≤12.1

1

1

18

4

≤12.1

1

1.0

`placeholder`

4

12

4

10

≤12.1

5

≤37

18

4

≤12.1

5

1.0

`readOnly`

1

12

1

5

≤12.1

1

1

18

4

≤12.1

1

1.0

`reportValidity`

40

17

49

No

27

10.1

40

40

64

27

10.3

4.0

`required`

4

12

4

10

≤12.1

5

≤37

18

4

≤12.1

5

1.0

`rows`

1

12

1

5

≤12.1

1

1

18

4

≤12.1

1

1.0

`select`

1

12

1

5

≤12.1

1

1

18

4

≤12.1

1

1.0

`selectionDirection`

15

79

8

No

≤12.1

6

≤37

18

8

≤12.1

6

1.0

`selectionEnd`

1

12

1

9

≤12.1

1.3

1

18

4

≤12.1

1

1.0

`selectionStart`

1

12

1

9

≤12.1

1.3

1

18

4

≤12.1

1

1.0

`setCustomValidity`

4

12

4

10

≤12.1

5

≤37

18

4

≤12.1

5

1.0

`setRangeText`

24

79

27

No

15

6.1

≤37

25

27

14

7

1.5

`setSelectionRange`

1

12

1

9

≤12.1

1.3

1

18

4

≤12.1

1

1.0

`textLength`

4

17

1

No

≤12.1

5

≤37

18

4

≤12.1

4

1.0

`type`

1

12

1

5

≤12.1

1

1

18

4

≤12.1

1

1.0

`validationMessage`

5

12

4

10

≤12.1

5

≤37

18

4

≤12.1

5

1.0

`validity`

3

12

4

10

≤12.1

5

≤37

18

4

≤12.1

5

1.0

`value`

1

12

1

5

≤12.1

1

1

18

4

≤12.1

1

1.0

`willValidate`

1

12

4

10

≤12.1

4

1

18

4

≤12.1

3.2

1.0

`wrap`

16

12

4

5

≤12.1

6

≤37

18

4

≤12.1

6

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTextAreaElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTextAreaElement</a>
