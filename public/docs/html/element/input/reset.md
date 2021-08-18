&lt;input type="reset"&gt;
==========================

[`<input>`](../input) elements of type `reset` are rendered as buttons, with a default `click` event handler that resets all of the inputs in the form to their initial values.

You should usually avoid including reset buttons in your forms. They're rarely useful, and are instead more likely to frustrate users who click them by mistake (often while trying to click the [submit button](submit)).

<table><tbody><tr class="odd"><td><strong><a href="#value">Value</a></strong></td><td>A <a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMString"><code>DOMString</code></a> used as the button's label</td></tr><tr class="even"><td><strong>Events</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event"><code>click</code></a></td></tr><tr class="odd"><td><strong>Supported common attributes</strong></td><td><a href="../input#attr-type"><code>type</code></a> and <a href="../input#attr-value"><code>value</code></a></td></tr><tr class="even"><td><strong>IDL attributes</strong></td><td><code>value</code></td></tr><tr class="odd"><td><strong>Methods</strong></td><td>None</td></tr></tbody></table>

Value
-----

An `<input type="reset">` element's [`value`](../input#attr-value) attribute contains a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) that is used as the button's label. Buttons such as `reset` don't have a value otherwise.

    <input type="reset" value="Reset the form">

If you don't specify a `value`, you get an button with the default label (typically "Reset," but this will vary depending on the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)):

    <input type="reset">

Using reset buttons
-------------------

`<input type="reset">` buttons are used to reset forms. If you want to create a custom button and then customize the behavior using JavaScript, you need to use `<input type="button">`, or better still, a [`<button>`](../button) element.

### A simple reset button

We'll begin by creating a simple reset button:

    <form>
      <div>
        <label for="example">Type in some sample text</label>
        <input id="example" type="text">
      </div>
      <div>
        <input type="reset" value="Reset the form">
      </div>
    </form>

This renders like so:

Try entering some text into the text field, and then pressing the reset button.

### Adding a reset keyboard shortcut

To add a keyboard shortcut to a reset button — just as you would with any [`<input>`](../input) for which it makes sense — you use the [`accesskey`](../../global_attributes#attr-accesskey) global attribute.

In this example, r is specified as the access key (you'll need to press r plus the particular modifier keys for your browser/OS combination; see [`accesskey`](../../global_attributes#attr-accesskey) for a useful list of those).

    <form>
      <div>
        <label for="example">Type in some sample text</label>
        <input id="example" type="text">
      </div>
      <div>
        <input type="reset" value="Reset the form"
         accesskey="r">
      </div>
    </form>

The problem with the above example is that there's no way for the user to know what the access key is! This is especially true since the modifiers are typically non-standard to avoid conflicts. When building a site, be sure to provide this information in a way that doesn't interfere with the site design (for example by providing an easily accessible link that points to information on what the site access keys are). Adding a tooltip to the button (using the [`title`](../../global_attributes#attr-title) attribute) can also help, although it's not a complete solution for accessibility purposes.

### Disabling and enabling a reset button

To disable a reset button, specify the [`disabled`](../../global_attributes#attr-disabled) global attribute on it, like so:

    <input type="reset" value="Disabled" disabled>

You can enable and disable buttons at run time by setting `disabled` to `true` or `false`; in JavaScript this looks like `btn.disabled = true` or `btn.disabled = false`.

**Note**: See the `<input type="button">` page for more ideas about enabling and disabling buttons.

Validation
----------

Buttons don't participate in constraint validation; they have no real value to be constrained.

Examples
--------

We've included simple examples above. There isn't really anything more to say about reset buttons.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#reset-button-state-(type=reset)">HTML Living Standard<br />
<span class="small">The definition of '&lt;input type="reset"&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#reset-button-state-(type=reset)">HTML5<br />
<span class="small">The definition of '&lt;input type="reset"&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td></tr></tbody></table>

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

`reset`

1

12

1

Unlike other browsers, Firefox by default [persists the dynamic disabled state](http://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing) of a `<button>` across page loads. Use the `autocomplete` attribute to control this feature.

Yes

Yes

1

Yes

Yes

4

Unlike other browsers, Firefox by default [persists the dynamic disabled state](http://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing) of a `<button>` across page loads. Use the `autocomplete` attribute to control this feature.

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

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/reset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/reset</a>
