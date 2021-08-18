&lt;input type="submit"&gt;
===========================

[`<input>`](../input) elements of type `submit` are rendered as buttons. When the [`click`](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event) event occurs (typically because the user clicked the button), the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) attempts to submit the form to the server.

    <input type="submit" value="Send Request">

<table><tbody><tr class="odd"><td><strong><a href="#value">Value</a></strong></td><td>A <a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMString"><code>DOMString</code></a> used as the button's label</td></tr><tr class="even"><td><strong>Events</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event"><code>click</code></a></td></tr><tr class="odd"><td><strong>Supported common attributes</strong></td><td><a href="../input#attr-type"><code>type</code></a> and <a href="../input#attr-value"><code>value</code></a></td></tr><tr class="even"><td><strong>IDL attributes</strong></td><td><code>value</code></td></tr><tr class="odd"><td><strong>Methods</strong></td><td>None</td></tr></tbody></table>

Value
-----

An `<input type="submit">` element's [`value`](../input#attr-value) attribute contains a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) which is displayed as the button's label. Buttons do not have a true value otherwise.

    <input type="submit" value="Send Request">

If you don't specify a `value`, the button will have a default label, chosen by the user agent. This label is likely to be something along the lines of "Submit" or "Submit Query." Here's an example of a submit button with a default label in your browser:

    <input type="submit">

Additional attributes
---------------------

In addition to the attributes shared by all [`<input>`](../input) elements, `submit` button inputs support the following attributes:

<table><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>formaction</code></td><td>The URL to which to submit the form's data; overrides the form's <a href="../form#attr-action"><code>action</code></a> attribute, if any</td></tr><tr class="even"><td><code>formenctype</code></td><td>A string specifying the encoding type to use for the form data</td></tr><tr class="odd"><td><code>formmethod</code></td><td>The HTTP method (<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET"><code>get</code></a> or <a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST"><code>post</code></a>) to use when submitting the form.</td></tr><tr class="even"><td><code>formnovalidate</code></td><td>A Boolean which, if present, means the form's fields will not be subjected to <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation">constraint validation</a> before submitting the data to the server</td></tr><tr class="odd"><td><code>formtarget</code></td><td>The <a href="https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context">browsing context</a> into which to load the response returned by the server after submitting the form</td></tr></tbody></table>

### `formaction`

A string indicating the URL to which to submit the data. This takes precedence over the [`action`](../form#attr-action) attribute on the [`<form>`](../form) element that owns the [`<input>`](../input).

This attribute is also available on `<input type="image">` and [`<button>`](../button) elements.

### `formenctype`

A string that identifies the encoding method to use when submitting the form data to the server. There are three permitted values:

`application/x-www-form-urlencoded`  
This, the default value, sends the form data as a string after URL encoding the text using an algorithm such as [`encodeURI()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURI).

`multipart/form-data`  
Uses the [`FormData`](https://developer.mozilla.org/en-US/docs/Web/API/FormData) API to manage the data, allowing for files to be submitted to the server. You *must* use this encoding type if your form includes any [`<input>`](../input) elements of [`type`](../input#attr-type) `file` (`<input type="file">`).

`text/plain`  
Plain text; mostly useful only for debugging, so you can easily see the data that's to be submitted.

If specified, the value of the `formenctype` attribute overrides the owning form's [`action`](../form#attr-action) attribute.

This attribute is also available on `<input type="image">` and [`<button>`](../button) elements.

### `formmethod`

A string indicating the HTTP method to use when submitting the form's data; this value overrides any [`method`](../form#attr-method) attribute given on the owning form. Permitted values are:

`get`  
A URL is constructed by starting with the URL given by the `formaction` or [`action`](../form#attr-action) attribute, appending a question mark ("?") character, then appending the form's data, encoded as described by `formenctype` or the form's [`enctype`](../form#attr-enctype) attribute. This URL is then sent to the server using an HTTP [`get`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET) request. This method works well for simple forms that contain only ASCII characters and have no side effects. This is the default value.

`post`  
The form's data is included in the body of the request that is sent to the URL given by the `formaction` or [`action`](../form#attr-action) attribute using an HTTP [`post`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) method. This method supports complex data and file attachments.

`dialog`  
This method is used to indicate that the button closes the dialog with which the input is associated, and does not transmit the form data at all.

This attribute is also available on `<input type="image">` and [`<button>`](../button) elements.

### `formnovalidate`

A Boolean attribute which, if present, specifies that the form should not be validated before submission to the server. This overrides the value of the [`novalidate`](../form#attr-novalidate) attribute on the element's owning form.

This attribute is also available on `<input type="image">` and [`<button>`](../button) elements.

### `formtarget`

A string which specifies a name or keyword that indicates where to display the response received after submitting the form. The string must be the name of a **browsing context** (that is, a tab, window, or [`<iframe>`](../iframe). A value specified here overrides any target given by the [`target`](../form#attr-target) attribute on the [`<form>`](../form) that owns this input.

In addition to the actual names of tabs, windows, or inline frames, there are a few special keywords that can be used:

`_self`  
Loads the response into the same browsing context as the one that contains the form. This will replace the current document with the received data. This is the default value used if none is specified.

`_blank`  
Loads the response into a new, unnamed, browsing context. This is typically a new tab in the same window as the current document, but may differ depending on the configuration of the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent).

`_parent`  
Loads the response into the parent browsing context of the current one. If there is no parent context, this behaves the same as `_self`.

`_top`  
Loads the response into the top-level browsing context; this is the browsing context that is the topmost ancestor of the current context. If the current context is the topmost context, this behaves the same as `_self`.

This attribute is also available on `<input type="image">` and [`<button>`](../button) elements.

Using submit buttons
--------------------

`<input type="submit">` buttons are used to submit forms. If you want to create a custom button and then customize the behavior using JavaScript, you need to use `<input type="button">`, or better still, a [`<button>`](../button) element.

If you choose to use `<button>` elements to create the buttons in your form, keep this in mind: if there's only one `<button>` inside the [`<form>`](../form), that button will be treated as the "submit" button. So you should be in the habit of expressly specifying which button is the submit button.

### A simple submit button

We'll begin by creating a form with a simple submit button:

    <form>
      <div>
        <label for="example">Let's submit some text</label>
        <input id="example" type="text" name="text">
      </div>
      <div>
        <input type="submit" value="Send">
      </div>
    </form>

This renders like so:

Try entering some text into the text field, and then submitting the form.

Upon submitting, the data name/value pair gets sent to the server. In this instance, the string will be `text=usertext`, where "usertext" is the text entered by the user, encoded to preserve special characters. Where and how the data is submitted depends on the configuration of the `<form>`; see [Sending form data](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data) for more details.

### Adding a submit keyboard shortcut

Keyboard shortcuts, also known as access keys and keyboard equivalents, let the user trigger a button using a key or combination of keys on the keyboard. To add a keyboard shortcut to a submit button — just as you would with any [`<input>`](../input) for which it makes sense — you use the [`accesskey`](../../global_attributes#attr-accesskey) global attribute.

In this example, s is specified as the access key (you'll need to press s plus the particular modifier keys for your browser/OS combination. In order to avoid conflicts with the user agent's own keyboard shortcuts, different modifier keys are used for access keys than for other shortcuts on the host computer. See [`accesskey`](../../global_attributes#attr-accesskey) for further details.

Here's the previous example with the s access key added:

    <form>
      <div>
        <label for="example">Let's submit some text</label>
        <input id="example" type="text" name="text">
      </div>
      <div>
        <input type="submit" value="Send"
         accesskey="s">
      </div>
    </form>

For example, in Firefox for Mac, pressing Control-Option-S triggers the Send button, while Chrome on Windows uses Alt+S.

The problem with the above example is that the user will not know what the access key is! This is especially true since the modifiers are typically non-standard to avoid conflicts. When building a site, be sure to provide this information in a way that doesn't interfere with the site design (for example by providing an easily accessible link that points to information on what the site access keys are). Adding a tooltip to the button (using the [`title`](../../global_attributes#attr-title) attribute) can also help, although it's not a complete solution for accessibility purposes.

### Disabling and enabling a submit button

To disable a submit button, specify the [`disabled`](../../global_attributes#attr-disabled) global attribute on it, like so:

    <input type="submit" value="Disabled" disabled>

You can enable and disable buttons at run time by setting `disabled` to `true` or `false`; in JavaScript this looks like `btn.disabled = true` or `btn.disabled = false`.

See the `<input type="button">` page for more ideas about enabling and disabling buttons.

Validation
----------

Submit buttons don't participate in constraint validation; they have no real value to be constrained.

Examples
--------

We've included simple examples above. There isn't really anything more to say about submit buttons. There's a reason this kind of control is sometimes called a "simple button."

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#submit-button-state-(type=submit)">HTML Living Standard<br />
<span class="small">The definition of '&lt;input type="submit"&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#submit-button-state-(type=submit)">HTML5<br />
<span class="small">The definition of '&lt;input type="submit"&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`submit`

1

12

1

Unlike other browsers, Firefox by default [persists the dynamic disabled state](http://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing) of a across page loads. Use the `autocomplete` attribute to control this feature.

Yes

Yes

1

Yes

Yes

4

Unlike other browsers, Firefox by default [persists the dynamic disabled state](http://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing) of a across page loads. Use the `autocomplete` attribute to control this feature.

Yes

Yes

Yes

See also
--------

-   [`<input>`](../input) and the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) interface which implements it.
-   [Forms and buttons](https://developer.mozilla.org/en-US/docs/Learn/Forms/Basic_native_form_controls#actual_buttons)
-   [Forms (accessibility)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/forms)
-   [HTML forms](https://developer.mozilla.org/en-US/docs/Learn/Forms)
-   The [`<button>`](../button) element
-   [Compatibility of CSS properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/submit" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/submit</a>
