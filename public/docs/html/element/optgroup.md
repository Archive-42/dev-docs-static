&lt;optgroup&gt;
================

The `<optgroup>` creates a grouping of options within a [`<select>`](select) element.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td>Zero or more <a href="option"><code>&lt;option&gt;</code></a> elements.</td></tr><tr class="odd"><td>Tag omission</td><td>The start tag is mandatory. The end tag is optional if this element is immediately followed by another <code>&lt;optgroup&gt;</code> element, or if the parent element has no more content.</td></tr><tr class="even"><td>Permitted parents</td><td>A <a href="select"><code>&lt;select&gt;</code></a> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>group</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptGroupElement"><code>HTMLOptGroupElement</code></a></td></tr></tbody></table>

**Note**

Optgroup elements may not be nested.

Attributes
----------

This element includes the [global attributes](../global_attributes).

`disabled`  
If this Boolean attribute is set, none of the items in this option group is selectable. Often browsers grey out such control and it won't receive any browsing events, like mouse clicks or focus-related ones.

`label`  
The name of the group of options, which the browser can use when labeling the options in the user interface. This attribute is mandatory if this element is used.

Examples
--------

    <select>
      <optgroup label="Group 1">
        <option>Option 1.1</option>
      </optgroup>
      <optgroup label="Group 2">
        <option>Option 2.1</option>
        <option>Option 2.2</option>
      </optgroup>
      <optgroup label="Group 3" disabled>
        <option>Option 3.1</option>
        <option>Option 3.2</option>
        <option>Option 3.3</option>
      </optgroup>
    </select>

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#the-optgroup-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;optgroup&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#the-optgroup-element">HTML5<br />
<span class="small">The definition of '&lt;optgroup&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/interact/forms.html#h-17.6">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;optgroup&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`optgroup`

1

12

1

5.5

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

8

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

5.5

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

-   Other form-related elements: [`<form>`](form), [`<legend>`](legend), [`<label>`](label), [`<button>`](button), [`<select>`](select), [`<datalist>`](datalist), [`<option>`](option), [`<fieldset>`](fieldset), [`<textarea>`](textarea), [`<keygen>`](keygen), [`<input>`](input), [`<output>`](output), [`<progress>`](progress) and [`<meter>`](meter).

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/optgroup" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/optgroup</a>
