&lt;button&gt;: The Button element
==================================

The `<button>` represents a clickable button, used to submit [forms](https://developer.mozilla.org/en-US/docs/Learn/Forms) or anywhere in a document for accessible, standard button functionality. By default, HTML buttons are presented in a style resembling the platform the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) runs on, but you can change buttons’ appearance with [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS).

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#interactive_content">Interactive content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_listed">listed</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_labelable">labelable</a>, and <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_submittable">submittable</a> <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form-associated_content">form-associated</a> element, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a> but there must be no <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#interactive_content">Interactive content</a></td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>button</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>checkbox</code>, <code>link</code>, <code>menuitem</code>, <code>menuitemcheckbox</code>, <code>menuitemradio</code>, <code>option</code>, <code>radio</code>, <code>switch</code>, <code>tab</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLButtonElement"><code>HTMLButtonElement</code></a></td></tr></tbody></table>

Attributes
----------

This element's attributes include the [global attributes](../global_attributes).

`autofocus`  
This Boolean attribute specifies that the button should have input [focus](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/focus) when the page loads. **Only one element in a document can have this attribute.**

 `autocomplete` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
This attribute on a [`<button>`](button) is nonstandard and Firefox-specific. Unlike other browsers, [Firefox persists the dynamic disabled state](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing) of a [`<button>`](button) across page loads. Setting `autocomplete="off"` on the button disables this feature; see [bug 654072](https://bugzilla.mozilla.org/show_bug.cgi?id=654072).

`disabled`  
This Boolean attribute prevents the user from interacting with the button: it cannot be pressed or focused.

Firefox, unlike other browsers, [persists the dynamic disabled state](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing) of a [`<button>`](button) across page loads. Use the [`autocomplete`](#attr-autocomplete) attribute to control this feature.

`form`  
The [`<form>`](form) element to associate the button with (its *form owner*). The value of this attribute must be the `id` of a `<form>` in the same document. (If this attribute is not set, the `<button>` is associated with its ancestor `<form>` element, if any.)

This attribute lets you associate `<button>` elements to `<form>`s anywhere in the document, not just inside a `<form>`. It can also override an ancestor `<form>` element.

`formaction`  
The URL that processes the information submitted by the button. Overrides the [`action`](form#attr-action) attribute of the button's form owner. Does nothing if there is no form owner.

`formenctype`  
If the button is a submit button (it's inside/associated with a `<form>` and doesn't have `type="button"`), specifies how to encode the form data that is submitted. Possible values:

-   `application/x-www-form-urlencoded`: The default if the attribute is not used.
-   `multipart/form-data`: Use to submit [`<input>`](input) elements with their [`type`](input#attr-type) attributes set to `file`.
-   `text/plain`: Specified as a debugging aid; shouldn’t be used for real form submission.

If this attribute is specified, it overrides the [`enctype`](form#attr-enctype) attribute of the button's form owner.

`formmethod`  
If the button is a submit button (it's inside/associated with a `<form>` and doesn't have `type="button"`), this attribute specifies the [HTTP method](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods) used to submit the form. Possible values:

-   `post`: The data from the form are included in the body of the HTTP request when sent to the server. Use when the form contains information that shouldn’t be public, like login credentials.
-   `get`: The form data are appended to the form's `action` URL, with a `?` as a separator, and the resulting URL is sent to the server. Use this method when the form [has no side effects](https://developer.mozilla.org/en-US/docs/Glossary/Idempotent), like search forms.

If specified, this attribute overrides the [`method`](form#attr-method) attribute of the button's form owner.

`formnovalidate`  
If the button is a submit button, this Boolean attribute specifies that the form is not to be [validated](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation) when it is submitted. If this attribute is specified, it overrides the [`novalidate`](form#attr-novalidate) attribute of the button's form owner.

This attribute is also available on `<input type="image">` and `<input type="submit">` elements.

`formtarget`  
If the button is a submit button, this attribute is a author-defined name or standardized, underscore-prefixed keyword indicating where to display the response from submitting the form. This is the `name` of, or keyword for, a *browsing context* (a tab, window, or [`<iframe>`](iframe)). If this attribute is specified, it overrides the [`target`](form#attr-target) attribute of the button's form owner. The following keywords have special meanings:

-   `_self`: Load the response into the same browsing context as the current one. This is the default if the attribute is not specified.
-   `_blank`: Load the response into a new unnamed browsing context — usually a new tab or window, depending on the user’s browser settings.
-   `_parent`: Load the response into the parent browsing context of the current one. If there is no parent, this option behaves the same way as `_self`.
-   `_top`: Load the response into the top-level browsing context (that is, the browsing context that is an ancestor of the current one, and has no parent). If there is no parent, this option behaves the same way as `_self`.

`name`  
The name of the button, submitted as a pair with the button’s `value` as part of the form data.

`type`  
The default behavior of the button. Possible values are:

-   `submit`: The button submits the form data to the server. This is the default if the attribute is not specified for buttons associated with a `<form>`, or if the attribute is an empty or invalid value.
-   `reset`: The button resets all the controls to their initial values, like [&lt;input type="reset"&gt;](input/reset). (This behavior tends to annoy users.)
-   `button`: The button has no default behavior, and does nothing when pressed by default. It can have client-side scripts listen to the element's events, which are triggered when the events occur.

`value`  
Defines the value associated with the button’s `name` when it’s submitted with the form data. This value is passed to the server in params when the form is submitted.

Notes
-----

A submit button with the attribute `formaction` set, but without an associated form does nothing. You have to set a form owner, either by wrapping it in a `<form>` or set the attribute `form` to the id of the form.

`<button>` elements are much easier to style than [`<input>`](input) elements. You can add inner HTML content (think `<i>`, `<br>`, or even `<img>`), and use [`::after`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after) and [`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before) pseudo-elements for complex rendering.

If your buttons are not for submitting form data to a server, be sure to set their `type` attribute to `button`. Otherwise they will try to submit form data and to load the (nonexistent) response, possibly destroying the current state of the document.

Example
-------

    <button name="button">Press me</button>

Accessibility concerns
----------------------

### Icon buttons

Buttons that only show an icon to represent do not have an *accessible name*. Accessible names provide information for assistive technology, such as screen readers, to access when they parse the document and generate [an accessibility tree](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#accessibility_apis). Assistive technology then uses the accessibility tree to navigate and manipulate page content.

To give an icon button an accessible name, put text in the `<button>` element that concisely describes the button's functionality.

#### Example

    <button name="favorite">
      <svg aria-hidden="true" viewBox="0 0 10 10"><path d="M7 9L5 8 3 9V6L1 4h3l1-3 1 3h3L7 6z"/></svg>
      Add to favorites
    </button>

If you want to visually hide the button's text, an accessible way to do so is to use [a combination of CSS properties](https://gomakethings.com/hidden-content-for-better-a11y/#hiding-the-link) to remove it visually from the screen, but keep it parsable by assistive technology.

However, it is worth noting that leaving the button text visually apparent can aid people who may not be familiar with the icon's meaning or understand the button's purpose. This is especially relevant for people who are not technologically sophisticated, or who may have different cultural interpretations for the icon the button uses.

-   [What is an accessible name? | The Paciello Group](https://developer.paciellogroup.com/blog/2017/04/what-is-an-accessible-name/)
-   [MDN Understanding WCAG, Guideline 4.1 explanations](#)
-   [Understanding Success Criterion 4.1.2 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/ensure-compat-rsv.html)

### Size and Proximity

#### Size

Interactive elements such as buttons should provide an area large enough that it is easy to activate them. This helps a variety of people, including people with motor control issues and people using non-precise forms of input such as a stylus or fingers. A minimum interactive size of 44×44 [CSS pixels](https://www.w3.org/TR/WCAG21/#dfn-css-pixels) is recommended.

-   [Understanding Success Criterion 2.5.5: Target Size | W3C Understanding WCAG 2.1](https://www.w3.org/WAI/WCAG21/Understanding/target-size.html)
-   [Target Size and 2.5.5 | Adrian Roselli](https://adrianroselli.com/2019/06/target-size-and-2-5-5.html)
-   [Quick test: Large touch targets - The A11Y Project](https://a11yproject.com/posts/large-touch-targets/)

#### Proximity

Large amounts of interactive content — including buttons — placed in close visual proximity to each other should have space separating them. This spacing is beneficial for people who are experiencing motor control issues, who may accidentally activate the wrong interactive content.

Spacing may be created using CSS properties such as [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin).

-   [Hand tremors and the giant-button-problem - Axess Lab](https://axesslab.com/hand-tremors/)

### ARIA state information

To describe the state of a button the correct ARIA attribute to use is `aria-pressed` and not `aria-checked` or `aria-selected`. To find out more read the information about the [ARIA button role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/button_role).

### Firefox

Firefox will add a small dotted border on a focused button. This border is declared through CSS in the browser stylesheet, but you can override it to add your own focused style using `button::-moz-focus-inner { }`.

If overridden, it is important to **ensure that the state change when focus is moved to the button is high enough** that people experiencing low vision conditions will be able to perceive it.

Color contrast ratio is determined by comparing the luminosity of the button text and background color values compared to the background the button is placed on. In order to meet current [Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/intro/wcag), a ratio of 4.5:1 is required for text content and 3:1 for large text. (Large text is defined as 18.66px and [`bold`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight) or larger, or 24px or larger.)

-   [WebAIM: Color Contrast Checker](https://webaim.org/resources/contrastchecker/)
-   [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
-   [Understanding Success Criterion 1.4.3 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

### Clicking and focus

Whether clicking on a [`<button>`](button) causes it to (by default) become focused varies by browser and OS. The results for [`<input>`](input) of `type="button"` and `type="submit"` are the same.

<table><caption>Does clicking on a <a href="button"><code>&lt;button&gt;</code></a> give it focus?</caption><thead><tr class="header"><th>Desktop Browsers</th><th>Windows 8.1</th><th>OS X 10.X</th></tr></thead><tbody><tr class="odd"><td>Firefox</td><td>Yes - Firefox 30.0</td><td>No (even with a <code>tabindex</code>) Firefox 63</td></tr><tr class="even"><td>Chrome</td><td>Yes - Chrome 35</td><td>Yes - Chrome 65</td></tr><tr class="odd"><td>Safari</td><td>N/A</td><td>No (even with a <code>tabindex</code>) Safari 12 (<a href="https://bugs.webkit.org/show_bug.cgi?id=22261">bug 22261</a>)</td></tr><tr class="even"><td>Internet Explorer</td><td>Yes - Internet Explorer 11</td><td>N/A</td></tr><tr class="odd"><td>Presto</td><td>Yes - Opera 12</td><td>Yes - Opera 12</td></tr></tbody></table>

<table><caption>Does tapping on a <a href="button"><code>&lt;button&gt;</code></a> give it focus?</caption><thead><tr class="header"><th>Mobile Browsers</th><th>iOS 7.1.2</th><th>Android 4.4.4</th></tr></thead><tbody><tr class="odd"><td>Safari Mobile</td><td>No (even with a <code>tabindex</code>)</td><td>N/A</td></tr><tr class="even"><td>Chrome 35</td><td>No (even with a <code>tabindex</code>)</td><td>Yes</td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/form-elements.html#the-button-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;button&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#the-button-element">HTML5<br />
<span class="small">The definition of '&lt;button&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/interact/forms.html#h-17.5">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;button&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`button`

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

`autocomplete`

No

No

Yes

No

No

No

No

No

Yes

No

No

No

`autofocus`

5

12

4

10

9.6

5

37

18

4

?

?

1.0

`disabled`

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

`form`

Yes

16

Yes

No

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`formaction`

9

12

4

10

15

5.1

37

18

4

?

5

1.0

`formenctype`

9

12

4

10

10.6

?

37

18

4

?

?

1.0

`formmethod`

9

12

4

10

15

?

37

18

4

?

?

1.0

`formnovalidate`

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

`formtarget`

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

`type`

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

`value`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button</a>
