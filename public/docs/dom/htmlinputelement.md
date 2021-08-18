HTMLInputElement
================

The `HTMLInputElement` interface provides special properties and methods for manipulating the options, layout, and presentation of [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) elements.

Properties
----------

<table><caption>Properties related to the parent form</caption><tbody><tr class="odd"><td><code>form </code><span class="badge inline readonly">Read only </span></td><td><em><a href="htmlformelement"><code>HTMLFormElement</code></a> object:</em> <strong>Returns</strong> a reference to the parent <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form"><code>&lt;form&gt;</code></a> element.</td></tr><tr class="even"><td><code>formAction</code></td><td><em><code>string</code>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-formaction"><code>formaction</code></a> attribute, containing the URI of a program that processes information submitted by the element. This overrides the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-action"><code>action</code></a> attribute of the parent form.</td></tr><tr class="odd"><td><code>formEnctype</code></td><td><em><code>string</code>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-formenctype"><code>formenctype</code></a> attribute, containing the type of content that is used to submit the form to the server. This overrides the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-enctype"><code>enctype</code></a> attribute of the parent form.</td></tr><tr class="even"><td><code>formMethod</code></td><td><em><code>string</code>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-formmethod"><code>formmethod</code></a> attribute, containing the HTTP method that the browser uses to submit the form. This overrides the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-method"><code>method</code></a> attribute of the parent form.</td></tr><tr class="odd"><td><code>formNoValidate</code></td><td><em><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean"><code>Boolean</code></a>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-formnovalidate"><code>formnovalidate</code></a> attribute, indicating that the form is not to be validated when it is submitted. This overrides the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-novalidate"><code>novalidate</code></a> attribute of the parent form.</td></tr><tr class="even"><td><code>formTarget</code></td><td><em><code>string</code>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-formtarget"><code>formtarget</code></a> attribute, containing a name or keyword indicating where to display the response that is received after submitting the form. This overrides the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-target"><code>target</code></a> attribute of the parent form.</td></tr></tbody></table>

<table><caption>Properties that apply to any type of input element that is not hidden</caption><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><code>name</code></td><td><em><code>string</code>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-name"><code>name</code></a> attribute, containing a name that identifies the element when submitting the form.</td></tr><tr class="even"><td><code>type</code></td><td><em><code>string</code>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type"><code>type</code></a> attribute, indicating the type of control to display. See <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type"><code>type</code></a> attribute of <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input"><code>&lt;input&gt;</code></a> for possible values.</td></tr><tr class="odd"><td><code>disabled</code></td><td><em><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean"><code>Boolean</code></a>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-disabled"><code>disabled</code></a> attribute, indicating that the control is not available for interaction. The input values will not be submitted with the form. See also <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-readonly"><code>readonly</code></a></td></tr><tr class="even"><td><code>autofocus</code></td><td><em><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean"><code>Boolean</code></a>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-autofocus"><code>autofocus</code></a> attribute, which specifies that a form control should have input focus when the page loads, unless the user overrides it, for example by typing in a different control. Only one form element in a document can have the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-autofocus"><code>autofocus</code></a> attribute. It cannot be applied if the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type"><code>type</code></a> attribute is set to <code>hidden</code> (that is, you cannot automatically set focus to a hidden control).</td></tr><tr class="odd"><td><code>required</code></td><td><em><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean"><code>Boolean</code></a>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-required"><code>required</code></a> attribute, indicating that the user must fill in a value before submitting a form.</td></tr><tr class="even"><td><code>value</code></td><td><em><code>string</code>:</em> <strong>Returns / Sets</strong> the current value of the control.<p><strong>Note:</strong> If the user enters a value different from the value expected, this may return an empty string.</p></td></tr><tr class="odd"><td><code>validity</code> <span class="badge inline readonly">Read only </span></td><td><em><a href="validitystate"><code>ValidityState</code></a><code> object</code>:</em> <strong>Returns</strong> the element's current validity state.</td></tr><tr class="even"><td><code>validationMessage</code> <span class="badge inline readonly">Read only </span></td><td><em><code>string</code>:</em> <strong>Returns</strong> a localized message that describes the validation constraints that the control does not satisfy (if any). This is the empty string if the control is not a candidate for constraint validation (<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-willvalidate"><code>willvalidate</code></a> is <code>false</code>), or it satisfies its constraints. This value can be set by the <code>setCustomValidity</code> method.</td></tr><tr class="odd"><td><code>willValidate</code> <span class="badge inline readonly">Read only </span></td><td><em><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean"><code>Boolean</code></a>:</em> <strong>Returns</strong> whether the element is a candidate for constraint validation. It is <code>false</code> if any conditions bar it from constraint validation, including: its <code>type</code> is <code>hidden</code>, <code>reset</code>, or <code>button</code>; it has a <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/datalist"><code>&lt;datalist&gt;</code></a> ancestor; its <code>disabled</code> property is <code>true</code>.</td></tr></tbody></table>

<table><caption>Properties that apply only to elements of type <code>checkbox</code> or <code>radio</code> </caption><tbody><tr class="odd"><td><code>checked</code></td><td><em><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean"><code>Boolean</code></a>:</em> <strong>Returns / Sets</strong> the current state of the element when <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type"><code>type</code></a> is <code>checkbox</code> or <code>radio</code>.</td></tr><tr class="even"><td><code>defaultChecked</code></td><td><em><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean"><code>Boolean</code></a>:</em> <strong>Returns / Sets</strong> the default state of a radio button or checkbox as originally specified in HTML that created this object.</td></tr><tr class="odd"><td><code id="indeterminate">indeterminate</code></td><td><em><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean"><code>Boolean</code></a>:</em> <strong>Returns</strong> whether the checkbox or radio button is in indeterminate state. For checkboxes, the effect is that the appearance of the checkbox is obscured/greyed in some way as to indicate its state is indeterminate (not checked but not unchecked). Does not affect the value of the <code>checked</code> attribute, and clicking the checkbox will set the value to false.</td></tr></tbody></table>

<table><caption>Properties that apply only to elements of type <code>image</code> </caption><tbody><tr class="odd"><td><code>alt</code></td><td><em><code>string</code>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-alt"><code>alt</code></a> attribute, containing alternative text to use when <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type"><code>type</code></a> is <code>image.</code></td></tr><tr class="even"><td><code>height</code></td><td><em><code>string</code>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-height"><code>height</code></a> attribute, which defines the height of the image displayed for the button, if the value of <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type"><code>type</code></a> is <code>image</code>.</td></tr><tr class="odd"><td><code>src</code></td><td><code>string</code><em>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-src"><code>src</code></a> attribute, which specifies a URI for the location of an image to display on the graphical submit button, if the value of <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type"><code>type</code></a> is <code>image</code>; otherwise it is ignored.</td></tr><tr class="even"><td><code>width</code></td><td><code>string</code><em>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-width"><code>width</code></a> attribute, which defines the width of the image displayed for the button, if the value of <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type"><code>type</code></a> is <code>image</code>.</td></tr></tbody></table>

<table><caption>Properties that apply only to elements of type <code>file</code> </caption><tbody><tr class="odd"><td><code>accept</code></td><td><em><code>string</code>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-accept"><code>accept</code></a> attribute, containing comma-separated list of file types accepted by the server when <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type"><code>type</code></a> is <code>file</code>.</td></tr><tr class="even"><td><code>allowdirs</code> <span class="icon non-standard" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This API has not been standardized. </span></td><td><em><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean"><code>Boolean</code></a>:</em> Part of the non-standard Directory Upload API; <strong>indicates</strong> whether or not to allow directories and files both to be selected in the file list. Implemented only in Firefox and is hidden behind a preference.</td></tr><tr class="odd"><td><code id="files_prop">files</code></td><td><strong>Returns/accepts</strong> a <a href="filelist"><code>FileList</code></a> object, which contains a list of <a href="file"><code>File</code></a> objects representing the files selected for upload.</td></tr><tr class="even"><td><a href="htmlinputelement/webkitdirectory"><code>webkitdirectory</code></a> <span class="icon non-standard" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This API has not been standardized. </span></td><td><em><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean"><code>Boolean</code></a>:</em> <strong>Returns</strong> the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-webkitdirectory"><code>webkitdirectory</code></a> attribute; if true, the file system picker interface only accepts directories instead of files.</td></tr><tr class="odd"><td><a href="htmlinputelement/webkitentries"><code>webkitEntries</code></a> <span class="icon non-standard" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This API has not been standardized. </span></td><td><em>Array of <a href="filesystementry"><code>FileSystemEntry</code></a> objects:</em> <strong>Describes</strong> the currently selected files or directories.</td></tr></tbody></table>

<table><caption>Properties that apply only to <code>text/number</code>-containing or elements</caption><tbody><tr class="odd"><td><code>autocomplete</code></td><td><em><code>string</code>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-autocomplete"><code>autocomplete</code></a> attribute, indicating whether the value of the control can be automatically completed by the browser. Ignored if the value of the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type"><code>type</code></a> attribute is <code>hidden</code>, <code>checkbox</code>, <code>radio</code>, <code>file</code>, or a button type (<code>button</code>, <code>submit</code>, <code>reset</code>, <code>image</code>). Possible values are:<br />
<code>on</code>: the browser can autocomplete the value using previously stored value<br />
<code>off</code>: the user must explicity enter a value</td></tr><tr class="even"><td><code>max</code></td><td><em><code>string</code>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-max"><code>max</code></a> attribute, containing the maximum (numeric or date-time) value for this item, which must not be less than its minimum (<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-min"><code>min</code></a> attribute) value.</td></tr><tr class="odd"><td><code>maxLength</code></td><td><em><code>long</code>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-maxlength"><code>maxlength</code></a> attribute, containing the <span class="underline"><strong>maximum number of characters</strong></span> (in Unicode code points) that the value can have. (If you set this to a negative number, an exception will be thrown.)</td></tr><tr class="even"><td><code>min</code></td><td><em><code>string</code>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-min"><code>min</code></a> attribute, containing the minimum (numeric or date-time) value for this item, which must not be greater than its maximum (<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-max"><code>max</code></a> attribute) value.</td></tr><tr class="odd"><td><code>minLength</code></td><td><em><code>long</code>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-minlength"><code>minlength</code></a> attribute, containing the <span class="underline"><strong>minimum number of characters</strong></span> (in Unicode code points) that the value can have. (If you set this to a negative number, an exception will be thrown.)</td></tr><tr class="even"><td><code>pattern</code></td><td><em><code>string</code>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-pattern"><code>pattern</code></a> attribute, containing a <span class="underline"><strong>regular expression</strong></span> that the control's value is checked against. Use the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-title"><code>title</code></a> attribute to describe the pattern to help the user. This attribute applies when the value of the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type"><code>type</code></a> attribute is <code>text</code>, <code>search</code>, <code>tel</code>, <code>url</code> or <code>email</code>; otherwise it is ignored.</td></tr><tr class="odd"><td><code>placeholder</code></td><td><em><code>string</code>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-placeholder"><code>placeholder</code></a> attribute, containing a hint to the user of what can be entered in the control. The placeholder text must not contain carriage returns or line-feeds. This attribute applies when the value of the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type"><code>type</code></a> attribute is <code>text</code>, <code>search</code>, <code>tel</code>, <code>url</code> or <code>email</code>; otherwise it is ignored.</td></tr><tr class="even"><td><code>readOnly</code></td><td><em><code>boolean</code>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-readonly"><code>readonly</code></a> attribute, indicating that the user cannot modify the value of the control.<br />
This is ignored if the value of the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type"><code>type</code></a> attribute is <code>hidden</code>, <code>range</code>, <code>color</code>, <code>checkbox</code>, <code>radio</code>, <code>file</code>, or a button type.</td></tr><tr class="odd"><td><code>selectionStart</code></td><td><em><code>unsigned long</code>:</em> <strong>Returns / Sets</strong> the beginning index of the selected text. When nothing is selected, this returns the position of the text input cursor (caret) inside of the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input"><code>&lt;input&gt;</code></a> element.</td></tr><tr class="even"><td><code>selectionEnd</code></td><td><em><code>unsigned long</code>:</em> <strong>Returns / Sets</strong> the end index of the selected text. When there's no selection, this returns the offset of the character immediately following the current text input cursor position.</td></tr><tr class="odd"><td><code>selectionDirection</code></td><td><em><code>string</code>:</em> <strong>Returns / Sets</strong> the direction in which selection occurred. Possible values are:<br />
<code>forward</code> if selection was performed in the start-to-end direction of the current locale<br />
<code>backward</code> for the opposite direction<br />
<code>none</code> if the direction is unknown</td></tr><tr class="even"><td><code>size</code></td><td><em><code>unsigned long</code>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-size"><code>size</code></a> attribute, containing <span class="underline"><strong>visual size of the control</strong></span>. This value is in pixels unless the value of <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type"><code>type</code></a> is <code>text</code> or <code>password</code>, in which case, it is an integer number of characters. Applies only when <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type"><code>type</code></a> is set to <code>text</code>, <code>search</code>, <code>tel</code>, <code>url</code>, <code>email</code>, or <code>password</code>; otherwise it is ignored.</td></tr></tbody></table>

<table><caption>Properties not yet categorized</caption><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><code>defaultValue</code></td><td><em><code>string</code>:</em> <strong>Returns / Sets</strong> the default value as originally specified in the HTML that created this object.</td></tr><tr class="even"><td><code>dirName</code></td><td><em><code>string</code>:</em> <strong>Returns / Sets</strong> the directionality of the element.</td></tr><tr class="odd"><td><code>accessKey</code></td><td><em><code>string</code>:</em> <strong>Returns</strong> a string containing a single character that switches input focus to the control when pressed.</td></tr><tr class="even"><td><code>list</code> <span class="badge inline readonly">Read only </span></td><td><em><a href="htmlelement"><code>HTMLElement</code></a><code> object</code>:</em> <strong>Returns</strong> the element pointed by the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-list"><code>list</code></a> attribute. The property may be <code>null</code> if no HTML element found in the same tree.</td></tr><tr class="odd"><td><code>multiple</code></td><td><em><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean"><code>Boolean</code></a>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-multiple"><code>multiple</code></a> attribute, indicating whether more than one value is possible (e.g., multiple files).</td></tr><tr class="even"><td><code>files</code></td><td><em><a href="filelist"><code>FileList</code></a><code> array</code>:</em> <strong>Returns</strong> the list of selected files.</td></tr><tr class="odd"><td><a href="htmlinputelement/labels"><code>HTMLInputElement.labels</code></a> <span class="badge inline readonly">Read only </span></td><td><em><a href="nodelist"><code>NodeList</code></a><code> array</code>:</em> <strong>Returns</strong> a list of <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label"><code>&lt;label&gt;</code></a> elements that are labels for this element.</td></tr><tr class="even"><td><code>step</code></td><td><code>string</code><em>:</em> <strong>Returns / Sets</strong> the element's <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-step"><code>step</code></a> attribute, which works with <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-min"><code>min</code></a> and <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-max"><code>max</code></a> to limit the increments at which a numeric or date-time value can be set. It can be the string <code>any</code> or a positive floating point number. If this is not set to <code>any</code>, the control accepts only values at multiples of the step value greater than the minimum.</td></tr><tr class="odd"><td><code>valueAsDate</code></td><td><em><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date"><code>Date</code></a><code> object</code>:</em> <strong>Returns / Sets</strong> the value of the element, interpreted as a date, or <code>null</code> if conversion is not possible.</td></tr><tr class="even"><td><code>valueAsNumber</code></td><td><em><code>double</code>:</em> <strong>Returns</strong> the value of the element, interpreted as one of the following, in order:<ul><li>A time value</li><li>A number</li><li><code>NaN</code> if conversion is impossible</li></ul></td></tr><tr class="odd"><td><code>autocapitalize</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td><code>string</code><em>:</em> <strong>Defines</strong> the capitalization behavior for user input. Valid values are <code>none</code>, <code>off</code>, <code>characters</code>, <code>words</code>, or <code>sentences</code>.</td></tr><tr class="even"><td><code>inputmode</code></td><td>Provides a hint to browsers as to the type of virtual keyboard configuration to use when editing this element or its contents.</td></tr></tbody></table>

 <span class="page-not-created">`HTMLInputElement.align`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
`string`*:* **Represents** the alignment of the element. *Use CSS instead.*

 <span class="page-not-created">`HTMLInputElement.useMap`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
`string`*:* **Represents** a client-side image map.

Methods
-------

<table><tbody><tr class="odd"><td><a href="htmlorforeignelement/blur"><code>blur()</code></a></td><td>Removes focus from the input element; keystrokes will subsequently go nowhere.</td></tr><tr class="even"><td><a href="htmlelement/click"><code>click()</code></a></td><td>Simulates a click on the input element.</td></tr><tr class="odd"><td><a href="htmlorforeignelement/focus"><code>focus()</code></a></td><td>Focuses on the input element; keystrokes will subsequently go to this element.</td></tr><tr class="even"><td><a href="htmlinputelement/select"><code>select()</code></a></td><td>Selects all the text in the input element, and focuses it so the user can subsequently replace all of its content.</td></tr><tr class="odd"><td><a href="htmlinputelement/setselectionrange"><code>setSelectionRange()</code></a></td><td>Selects a range of text in the input element (but does not focus it).</td></tr><tr class="even"><td><a href="htmlinputelement/setrangetext"><code>setRangeText()</code></a></td><td>Replaces a range of text in the input element with new text.</td></tr><tr class="odd"><td><code>setCustomValidity()</code></td><td>Sets a custom validity message for the element. If this message is not the empty string, then the element is suffering from a custom validity error, and does not validate.</td></tr><tr class="even"><td><code>checkValidity()</code></td><td>Returns a <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean"><code>Boolean</code></a> that is <code>false</code> if the element is a candidate for constraint validation, and it does not satisfy its constraints. In this case, it also fires an <code>invalid</code> event at the element. It returns <code>true</code> if the element is not a candidate for constraint validation, or if it satisfies its constraints.</td></tr><tr class="odd"><td><code>reportValidity()</code></td><td>Runs the <code>checkValidity()</code> method, and if it returns false (for an invalid input or no pattern attribute provided), then it reports to the user that the input is invalid in the same manner as if you submitted a form.</td></tr></tbody></table>

[`HTMLInputElement.stepDown()`](htmlinputelement/stepdown)  
Decrements the [`value`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-value) by ([`step`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-step) \* n), where n defaults to 1 if not specified. Throws an INVALID\_STATE\_ERR exception:

-   if the method is not applicable to for the current [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type) value,
-   if the element has no [`step`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-step) value,
-   if the [`value`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-value) cannot be converted to a number,
-   if the resulting value is above the [`max`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-max) or below the [`min`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-min).

[`HTMLInputElement.stepUp()`](htmlinputelement/stepup)  
Increments the [`value`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-value) by ([`step`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-step) \* n), where n defaults to 1 if not specified. Throws an INVALID\_STATE\_ERR exception:

-   if the method is not applicable to for the current [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type) value.,
-   if the element has no [`step`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-step) value,
-   if the [`value`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-value) cannot be converted to a number,
-   if the resulting value is above the [`max`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-max) or below the [`min`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-min).

 <span class="page-not-created">`HTMLInputElement.mozSetFileArray()`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Sets the files selected on the input to the given array of [`File`](file) objects. This is an alternative to `mozSetFileNameArray()` which can be used in frame scripts: a chrome script can [open files as File objects](https://developer.mozilla.org/en-US/docs/Extensions/Using_the_DOM_File_API_in_chrome_code) and send them via [message manager](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Multiprocess_Firefox/The_message_manager).

 [`HTMLInputElement.mozGetFileNameArray()`](htmlinputelement/mozgetfilenamearray) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns an array of all the file names from the input.

 [`HTMLInputElement.mozSetFileNameArray()`](htmlinputelement) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Sets the filenames for the files selected on the input. Not for use in [frame scripts](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Multiprocess_Firefox/Limitations_of_frame_scripts), because it accesses the file system.

Events
------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface:

[`input`](htmlelement/input_event)  
Fires when the `value` of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element has been changed. Note that this is actually fired on the [`HTMLElement`](htmlelement) interface and also applies to `contenteditable` elements, but we've listed it here because it is most commonly used with form input elements.  
Also available via the `oninput` event handler property.

`invalid`  
Fired when an element does not satisfy its constraints during constraint validation.  
Also available via the `oninvalid` event handler property.

`search`  
Fired when a search is initiated on an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) of `type="search"`.  
Also available via the `onsearch` event handler property.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlinputelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLInputElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#the-input-element">HTML5<br />
<span class="small">The definition of 'HTMLInputElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Technically, the <code>tabindex</code> and <code>accesskey</code> properties, as well as the <code>blur()</code>, <code>click()</code>, and <code>focus()</code> methods, are now defined on <a href="htmlelement"><code>HTMLElement</code></a>.<br />
The following properties are now obsolete: <code>align</code> and <code>useMap</code>.<br />
The following properties have been added: <code>autocomplete</code>, <code>autofocus</code>, <code>dirName</code>, <code>files</code>, <code>formAction</code>, <code>formEnctype</code>, <code>formMethod</code>, <code>formNoValidate</code>, <code>formTarget</code>, <code>height</code>, <code>indeterminate</code>, <code>labels</code>, <code>list</code>, <code>max</code>, <code>min</code>, <code>multiple</code>, <code>pattern</code>, <code>placeholder</code>, <code>required</code>, <code>selectionDirection</code>, <code>selectionEnd</code>, <code>selectionStart</code>, <code>step</code>, <code>validationMessage</code>, <code>validity</code>, <code>valueAsDate</code>, <code>valueAsNumber</code>, <code>width</code>, and <code>willValidate</code>.<br />
The following methods have been added: <code>checkValidity()</code>, <code>setCustomValidity()</code>, <code>setSelectionRange()</code>, <code>stepUp()</code>, and <code>stepDown()</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-6043025">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLInputElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>The <code>size</code> property is now an <code>unsigned long</code>. The <code>type</code> property must be entirely given in lowercase characters.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-6043025">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLInputElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`HTMLInputElement`

1

12

1

5.5

8

1

1

18

4

10.1

1

1.0

`accept`

1

12

1

6

≤12.1

1

1

18

4

≤12.1

1

1.0

`align`

1

12

1

5.5

≤12.1

1

1

18

4

≤12.1

1

1.0

`alt`

1

12

1

5.5

≤12.1

1

1

18

4

≤12.1

1

1.0

`autocomplete`

14

12

4

10

≤12.1

6

≤37

18

4

≤12.1

6

1.0

`autofocus`

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

`capture`

No

No

No

No

No

No

Yes

Yes

Yes

Yes

Yes

Yes

`checked`

1

12

1

5.5

≤12.1

1

1

18

4

≤12.1

1

1.0

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

4

1.0

`defaultChecked`

1

12

1

5.5

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

5.5

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

5.5

≤12.1

1

1

18

4

≤12.1

1

1.0

`files`

1

12

3

10

This property is read-only.

≤12.1

4

1

18

4

≤12.1

3

1.0

`form`

1

12

1

5.5

≤12.1

1

1

18

4

≤12.1

1

1.0

`formAction`

9

12

4

10

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`formEnctype`

9

12

4

Yes

≤12.1

5.1

≤37

18

4

≤12.1

5.1

1.0

`formMethod`

9

12

4

10

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`formNoValidate`

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

4

1.0

`formTarget`

9

12

4

10

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`height`

21

12

16

5.5

≤12.1

6.1

≤37

25

16

≤12.1

6

1.5

`incremental`

10

79

No

No

15

5.1

≤37

18

No

14

5

1.0

`indeterminate`

1

12

3.6

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`invalid_event`

10

12

4

10

10

5

4

18

64

12

5

4.0

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

`list`

20

12

4

10

≤12.1

12.1

≤37

25

4

≤12.1

12.2

1.5

`max`

4

12

16

10

≤12.1

5

≤37

18

16

≤12.1

4

1.0

`maxLength`

1

12

1

5.5

≤12.1

1

1

18

4

≤12.1

1

1.0

`min`

4

12

16

10

≤12.1

5

≤37

18

16

≤12.1

4

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

`multiple`

2

12

3.6

10

≤12.1

4

≤37

18

4

≤12.1

3.2

1.0

`name`

1

12

1

5.5

≤12.1

1

1

18

4

≤12.1

1

1.0

`onsearch`

1

79

No

No

15

1.3

1

18

No

14

1

1.0

`pattern`

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

4

1.0

`placeholder`

3

12

4

10

≤12.1

4

≤37

18

4

≤12.1

3.2

1.0

`readOnly`

1

12

1

5.5

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

4

1.0

`search_event`

Yes

79

No

No

Yes

Yes

Yes

Yes

No

?

?

Yes

`select`

1

12

1

5.5

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

13

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

4

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

8

3

1

18

4

10.1

1

1.0

`size`

1

12

1

5.5

≤12.1

1

1

18

4

≤12.1

1

1.0

`src`

1

12

1

5.5

≤12.1

1

1

18

4

≤12.1

1

1.0

`step`

5

12

16

10

≤12.1

5

≤37

18

16

≤12.1

4

1.0

`stepDown`

5

12

16

Does not have a specific UI. There are still differences with the latest spec; see [bug 835773](https://bugzil.la/835773).

10

≤12.1

5

≤37

18

16

Does not have a specific UI. There are still differences with the latest spec; see [bug 835773](https://bugzil.la/835773).

≤12.1

4

1.0

`stepUp`

5

12

16

Does not have a specific UI. There are still differences with the latest spec; see [bug 835773](https://bugzil.la/835773).

10

≤12.1

5

≤37

18

16

Does not have a specific UI. There are still differences with the latest spec; see [bug 835773](https://bugzil.la/835773).

≤12.1

4

1.0

`type`

1

12

1

5.5

≤12.1

1

1

18

4

≤12.1

1

1.0

`useMap`

1

12

1

6

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

4

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

4

1.0

`value`

1

12

1

5.5

≤12.1

1

1

18

4

≤12.1

1

1.0

`valueAsDate`

5

12

57

20-24

No

≤12.1

5

≤37

18

57

20-24

≤12.1

4

1.0

`valueAsNumber`

5

12

16

10

≤12.1

5

≤37

18

16

≤12.1

4

1.0

`webkitdirectory`

6

13

50

No

15

11.1

≤37

18

50

14

11.3

1.0

`webkitEntries`

22

79

50

No

15

11.1

≤37

25

No

14

11.3

1.5

`width`

21

12

16

5.5

≤12.1

6.1

≤37

25

16

≤12.1

6

1.5

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

3

1.0

See also
--------

-   HTML element implementing this interface: [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement</a>
