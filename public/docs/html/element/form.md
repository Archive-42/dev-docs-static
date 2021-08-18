&lt;form&gt;
============

The `<form>` represents a document section containing interactive controls for submitting information.

It is possible to use the [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid) and [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) CSS [pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) to style a `<form>` element based on whether or not the [`elements`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements) inside the form are valid.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#palpable_content">palpable content</a></td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, but not containing <code>&lt;form&gt;</code> elements</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a></td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>form</code> if the form has an <a href="https://www.w3.org/TR/accname-1.1/#dfn-accessible-name">accessible name</a>, otherwise <a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">no corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>search</code>, <code>none</code> or <code>presentation</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement"><code>HTMLFormElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

 `accept` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Comma-separated [content types](https://developer.mozilla.org/en-US/docs/Web/SVG/Content_type) the server accepts.

**Note**
**This attribute was removed in HTML5 and should not be used.** Instead, use the [`accept`](input#attr-accept) attribute on `<input type=file>` elements.

`accept-charset`  
Space-separated [character encodings](https://developer.mozilla.org/en-US/docs/Web/Guide/Localizations_and_character_encodings) the server accepts. The browser uses them in the order in which they are listed. The default value means [the same encoding as the page](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Encoding).  
(In previous versions of HTML, character encodings could also be delimited by commas.)

 `autocapitalize` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
A nonstandard attribute used by iOS Safari that controls how textual form elements should be automatically capitalized. `autocapitalize` attributes on a form elements override it on `<form>`. Possible values:

-   `none`: No automatic capitalization.
-   `sentences` (default): Capitalize the first letter of each sentence.
-   `words`: Capitalize the first letter of each word.
-   `characters`: Capitalize all characters — that is, uppercase.

`autocomplete`  
Indicates whether input elements can by default have their values automatically completed by the browser. `autocomplete` attributes on form elements override it on `<form>`. Possible values:

-   `off`: The browser may not automatically complete entries. (Browsers tend to ignore this for suspected login forms; see [The autocomplete attribute and login fields](https://developer.mozilla.org/en-US/docs/Web/Security/Securing_your_site/Turning_off_form_autocompletion#the_autocomplete_attribute_and_login_fields).)
-   `on`: The browser may automatically complete entries.

`name`  
The name of the form. The value must not be the empty string, and must be unique among the `form` elements in the forms collection that it is in, if any.

`rel`  
Creates a hyperlink or annotation depending on the value, see the [`rel`](../attributes/rel) attribute for details.

### Attributes for form submission

The following attributes control behavior during form submission.

`action`  
The URL that processes the form submission. This value can be overridden by a [`formaction`](button#attr-formaction) attribute on a [`<button>`](button), `<input type="submit">`, or `<input type="image">` element.

`enctype`  
If the value of the `method` attribute is `post`, `enctype` is the [MIME type](https://en.wikipedia.org/wiki/Mime_type) of the form submission. Possible values:

-   `application/x-www-form-urlencoded`: The default value.
-   `multipart/form-data`: Use this if the form contains [`<input>`](input) elements with `type=file`.
-   `text/plain`: Introduced by HTML5 for debugging purposes.

This value can be overridden by [`formenctype`](button#attr-formenctype) attributes on [`<button>`](button), `<input type="submit">`, or `<input type="image">` elements.

`method`  
The [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP) method to submit the form with. Possible (case insensitive) values:

-   `post`: The [POST method](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html#sec9.5); form data sent as the [request body](https://developer.mozilla.org/en-US/docs/Web/API/Body).
-   `get`: The [GET method](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html#sec9.3); form data appended to the `action` URL with a `?` separator. Use this method when the form [has no side-effects](https://developer.mozilla.org/en-US/docs/Glossary/Idempotent).
-   `dialog`: When the form is inside a [`<dialog>`](dialog), closes the dialog on submission.

This value is overridden by [`formmethod`](button#attr-formmethod) attributes on [`<button>`](button), `<input type="submit">`, or `<input type="image"> `elements.

`novalidate`  
This Boolean attribute indicates that the form shouldn't be validated when submitted. If this attribute is not set (and therefore the form ***is*** validated), it can be overridden by a [`formnovalidate`](button#attr-formnovalidate) attribute on a [`<button>`](button), `<input type="submit">`, or `<input type="image">` element belonging to the form.

`target`  
Indicates where to display the response after submitting the form. In HTML 4, this is the name/keyword for a frame. In HTML5, it is a name/keyword for a *browsing context* (for example, tab, window, or iframe). The following keywords have special meanings:

-   `_self` (default): Load into the same browsing context as the current one.
-   `_blank`: Load into a new unnamed browsing context.
-   `_parent`: Load into the parent browsing context of the current one. If no parent, behaves the same as `_self`.
-   `_top`: Load into the top-level browsing context (i.e., the browsing context that is an ancestor of the current one and has no parent). If no parent, behaves the same as `_self`.

This value can be overridden by a [`formtarget`](button#attr-formtarget) attribute on a [`<button>`](button), `<input type="submit">`, or `<input type="image">` element.

**Note**
Setting `target="_blank"` on `<form>` elements implicitly provides the same `rel` behavior as setting `rel="noopener"` which does not set `window.opener`.

Examples
--------

### HTML

    <!-- Form which will send a GET request to the current URL -->
    <form>
      <label>Name:
        <input name="submitted-name" autocomplete="name">
      </label>
      <button>Save</button>
    </form>

    <!-- Form which will send a POST request to the current URL -->
    <form method="post">
      <label>Name:
        <input name="submitted-name" autocomplete="name">
      </label>
      <button>Save</button>
    </form>

    <!-- Form with fieldset, legend, and label -->
    <form method="post">
      <fieldset>
        <legend>Title</legend>
        <label><input type="radio" name="radio"> Select me</label>
      </fieldset>
    </form>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#the-form-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;form&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#the-form-element">HTML5<br />
<span class="small">The definition of '&lt;form&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/interact/forms.html#h-17.3">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;form&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`form`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`accept`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`accept-charset`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`action`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`autocapitalize`

No

No

No

No

No

No

No

No

No

No

Yes

No

`autocomplete`

Yes

The Google Chrome UI for auto-complete request varies, depending on whether `autocomplete` is set to `off` on `<input>` elements as well as their form. Specifically, when a form has `autocomplete` set to `off` and its `<input>` element's `autocomplete` attribute is not set, then if the user asks for autofill suggestions for the `<input>` element, Chrome might display a message saying 'autocomplete has been disabled for this form.' On the other hand, if both the form and the input element have `autocomplete` set to `off`, the browser will not display that message. For this reason, you should set `autocomplete` to `off` for each `<input>` that has custom auto-completion.

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`enctype`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`method`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`name`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`novalidate`

10

12

4

10

15

10.1

37

18

4

14

10.3

1.0

`target`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [HTML forms guide](https://developer.mozilla.org/en-US/docs/Learn/Forms)
-   Other elements that are used when creating forms: [`<button>`](button), [`<datalist>`](datalist), [`<fieldset>`](fieldset), [`<input>`](input),[`<keygen>`](keygen), [`<label>`](label), [`<legend>`](legend), [`<meter>`](meter), [`<optgroup>`](optgroup), [`<option>`](option), [`<output>`](output), [`<progress>`](progress), [`<select>`](select), [`<textarea>`](textarea).
-   Getting a list of the elements in the form: [`HTMLFormElement.elements`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements)
-   [ARIA: Form role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Form_Role)
-   [ARIA: Search role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Search_role)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form</a>
