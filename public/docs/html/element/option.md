&lt;option&gt;: The HTML Option element
=======================================

The `<option>` is used to define an item contained in a [`<select>`](select), an [`<optgroup>`](optgroup), or a [`<datalist>`](datalist) element. As such, `<option>` can represent menu items in popups and other lists of items in an HTML document.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td>Text, possibly with escaped characters (like <code>&amp;eacute;</code>).</td></tr><tr class="odd"><td>Tag omission</td><td>The start tag is mandatory. The end tag is optional if this element is immediately followed by another <code>&lt;option&gt;</code> element or an <a href="optgroup"><code>&lt;optgroup&gt;</code></a>, or if the parent element has no more content.</td></tr><tr class="even"><td>Permitted parents</td><td>A <a href="select"><code>&lt;select&gt;</code></a>, an <a href="optgroup"><code>&lt;optgroup&gt;</code></a> or a <a href="datalist"><code>&lt;datalist&gt;</code></a> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>option</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionElement"><code>HTMLOptionElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

`disabled`  
If this Boolean attribute is set, this option is not checkable. Often browsers grey out such control and it won't receive any browsing event, like mouse clicks or focus-related ones. If this attribute is not set, the element can still be disabled if one of its ancestors is a disabled [`<optgroup>`](optgroup) element.

`label`  
This attribute is text for the label indicating the meaning of the option. If the `label` attribute isn't defined, its value is that of the element text content.

`selected`  
If present, this Boolean attribute indicates that the option is initially selected. If the `<option>` element is the descendant of a [`<select>`](select) element whose [`multiple`](select#attr-multiple) attribute is not set, only one single `<option>` of this [`<select>`](select) element may have the `selected` attribute.

`value`  
The content of this attribute represents the value to be submitted with the form, should this option be selected. If this attribute is omitted, the value is taken from the text content of the option element.

Examples
--------

See [`<select>`](select) for examples.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/form-elements.html#the-option-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;option&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#the-option-element">HTML5<br />
<span class="small">The definition of '&lt;option&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/interact/forms.html#h-17.6">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;option&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`option`

1

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`disabled`

1

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`label`

1

12

1

\["Before 77, Firefox didn't display the value of the `label` attribute as option text if element's content was empty. See [bug 40545](https://bugzil.la/40545).", "Historically, Firefox has allowed keyboard and mouse events to bubble up from the `<option>` element to the parent `<select>` element, although this behavior is inconsistent across many browsers. For better Web compatibility (and for technical reasons), they will not bubble up when Firefox is in multi-process mode and the `<select>` element is displayed as a drop-down list. The behavior is unchanged if the `<select>` is presented inline and it has either the `multiple` attribute defined or a `size` attribute set to more than `1`. Rather than watching `<option>` elements for events, you should watch for [change](https://developer.mozilla.org/docs/Web/Events/change) events on `<select>`. See [bug 1090602](https://bugzil.la/1090602) for details.", "When Mozilla introduced dedicated content threads to Firefox (through the Electrolysis, or e10s, project), support for styling `<option>` elements was removed temporarily. Starting in Firefox 54, you can apply foreground and background colors to `<option>` elements again, using the `color` and `background-color` CSS properties. See [bug 910022](https://bugzil.la/910022) for more information. Note that this is still disabled in Linux due to lack of contrast (see [bug 1338283](https://bugzil.la/1338283) for progress on this)."\]

Yes

Yes

Yes

Yes

Yes

4

Before 77, Firefox didn't display the value of the `label` attribute as option text if element's content was empty. See [bug 40545](https://bugzil.la/40545).

Yes

Yes

Yes

`selected`

1

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`value`

1

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

See also
--------

-   Other form-related elements: [`<form>`](form), [`<legend>`](legend), [`<label>`](label), [`<button>`](button), [`<select>`](select), [`<datalist>`](datalist), [`<optgroup>`](optgroup), [`<fieldset>`](fieldset), [`<textarea>`](textarea), [`<keygen>`](keygen), [`<input>`](input), [`<output>`](output), [`<progress>`](progress) and [`<meter>`](meter).

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option</a>
