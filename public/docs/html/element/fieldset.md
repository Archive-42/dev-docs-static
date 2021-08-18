&lt;fieldset&gt;: The Field Set element
=======================================

The `<fieldset>` is used to group several controls as well as labels ([`<label>`](label)) within a web form.

As the example above shows, the `<fieldset>` element provides a grouping for a part of an HTML form, with a nested [`<legend>`](legend) element providing a caption for the `<fieldset>`. It takes few attributes, the most notable of which are `form`, which can contain the `id` of a [`<form>`](form) on the same page, allowing you to make the `<fieldset>` part of that `<form>` even if it is not nested inside it, and `disabled`, which allows you to disable the `<fieldset>` and all its contents in one go.

Attributes
----------

This element includes the [global attributes](../global_attributes).

`disabled`  
If this Boolean attribute is set, all form controls that are descendants of the `<fieldset>`, are disabled, meaning they are not editable and won't be submitted along with the [`<form>`](form). They won't receive any browsing events, like mouse clicks or focus-related events. By default browsers display such controls grayed out. Note that form elements inside the [`<legend>`](legend) element won't be disabled.

`form`  
This attribute takes the value of the [`id`](../global_attributes#attr-id) attribute of a [`<form>`](form) element you want the `<fieldset>` to be part of, even if it is not inside the form. Please note that usage of this is confusing — if you want the [`<input>`](input) elements inside the `<fieldset>` to be associated with the form, you need to use the `form` attribute directly on those elements. You can check which elements are associated with a form via JavaScript, using [`HTMLFormElement.elements`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements).

`name`  
The name associated with the group.

**Note**: The caption for the fieldset is given by the first [`<legend>`](legend) element nested inside it.

Styling with CSS
----------------

There are several special styling considerations for `<fieldset>`.

Its [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) value is `block` by default, and it establishes a [block formatting context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context). If the `<fieldset>` is styled with an inline-level `display` value, it will behave as `inline-block`, otherwise it will behave as `block`. By default there is a `2px` `groove` border surrounding the contents, and a small amount of default padding. The element has [`min-inline-size: min-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-inline-size) by default.

If a [`<legend>`](legend) is present, it is placed over the `block-start` border. The `<legend>` shrink-wraps, and also establishes a formatting context. The `display` value is blockified. (For example, `display: inline` behaves as `block`.)

There will be an anonymous box holding the contents of the `<fieldset>`, which inherits certain properties from the `<fieldset>`. If the `<fieldset>` is styled with `display: grid` or `display: inline-grid`, then the anonymous box will be a grid formatting context. If the `<fieldset>` is styled with `display: flex` or `display: inline-flex`, then the anonymous box will be a flex formatting context. Otherwise, it establishes a block formatting context.

You can feel free to style the `<fieldset>` and `<legend>` in any way you want to suit your page design.

Examples
--------

### Simple fieldset

This example shows a really simple `<fieldset>` example, with a `<legend>`, and a single control inside it.

    <form action="#">
      <fieldset>
        <legend>Simple fieldset</legend>
        <input type="radio" id="radio">
        <label for="radio">Spirit of radio</label>
      </fieldset>
    </form>

### Disabled fieldset

This example shows a disabled `<fieldset>` with two controls inside it. Note how both the controls are disabled due to being inside a disabled `<fieldset>`.

    <form action="#">
      <fieldset disabled>
        <legend>Disabled fieldset</legend>
        <div>
          <label for="name">Name: </label>
          <input type="text" id="name" value="Chris">
        </div>
        <div>
          <label for="pwd">Archetype: </label>
          <input type="password" id="pwd" value="Wookie">
        </div>
      </fieldset>
    </form>

Technical summary
-----------------

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines#sectioning_root">sectioning root</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_listed">listed</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form-associated_content">form-associated</a> element, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td>An optional <a href="legend"><code>&lt;legend&gt;</code></a> element, followed by flow content.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>group</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>radiogroup</code>, <code>presentation</code>, <code>none</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFieldSetElement"><code>HTMLFieldSetElement</code></a></td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#the-fieldset-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;fieldset&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Definition of the <code>fieldset</code> element</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#the-fieldset-element">HTML5<br />
<span class="small">The definition of '&lt;fieldset&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/interact/forms.html#h-17.10">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;fieldset&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`fieldset`

Yes

Does not support `flexbox` and `grid` layouts within this element. See [bug 262679](https://crbug.com/262679).

12

Does not support `flexbox` and `grid` layouts within this element. See [bug 4511145](https://developer.microsoft.com/microsoft-edge/platform/issues/4511145/).

Yes

Yes

Yes

Does not support `flexbox` and `grid` layouts within this element. See [bug 262679](https://crbug.com/262679).

Yes

Yes

Does not support `flexbox` and `grid` layouts within this element. See [bug 262679](https://crbug.com/262679).

Yes

Does not support `flexbox` and `grid` layouts within this element. See [bug 262679](https://crbug.com/262679).

Yes

Yes

Does not support `flexbox` and `grid` layouts within this element. See [bug 262679](https://crbug.com/262679).

Yes

Yes

Does not support `flexbox` and `grid` layouts within this element. See [bug 262679](https://crbug.com/262679).

`disabled`

Yes

12

Does not work with nested fieldsets. For example: `<fieldset disabled><fieldset><!--Still enabled--></fieldset></fieldset>`

Yes

Yes

Not all form control descendants of a disabled fieldset are properly disabled in IE11; see IE [bug 817488: input\[type='file'\] not disabled inside disabled fieldset](https://connect.microsoft.com/IE/feedbackdetail/view/817488) and IE [bug 962368: Can still edit input\[type='text'\] within fieldset\[disabled\]](https://connect.microsoft.com/IE/feedbackdetail/view/962368/can-still-edit-input-type-text-within-fieldset-disabled).

12

6

4.4

Yes

Yes

?

6

Yes

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

See also
--------

-   The [`<legend>`](legend) element
-   The [`<input>`](input) element
-   The [`<label>`](label) element
-   The [`<form>`](form) element

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset</a>
