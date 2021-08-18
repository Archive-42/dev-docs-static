&lt;slot&gt;
============

The `<slot>`—part of the [Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components) technology suite—is a placeholder inside a web component that you can fill with your own markup, which lets you create separate DOM trees and present them together.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a></td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#transparent_content_model">Transparent</a></td></tr><tr class="odd"><td>Events</td><td><code>slotchange</code></td></tr><tr class="even"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="odd"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a></td></tr><tr class="even"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="odd"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="even"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSlotElement"><code>HTMLSlotElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

`name`  
The slot's name.

A **named slot** is a `<slot>` element with a `name` attribute.

Examples
--------

    <template id="element-details-template">
      <style>
        details {font-family: "Open Sans Light", Helvetica, Arial, sans-serif }
        .name {font-weight: bold; color: #217ac0; font-size: 120% }
        h4 {
          margin: 10px 0 -8px 0;
          background: #217ac0;
          color: white;
          padding: 2px 6px;
          border: 1px solid #cee9f9;
          border-radius: 4px;
        }
        .attributes { margin-left: 22px; font-size: 90% }
        .attributes p { margin-left: 16px; font-style: italic }
      </style>
      <details>
        <summary>
          <code class="name">&lt;<slot name="element-name">NEED NAME</slot>&gt;</code>
          <i class="desc"><slot name="description">NEED DESCRIPTION</slot></i>
        </summary>
        <div class="attributes">
          <h4>Attributes</h4>
          <slot name="attributes"><p>None</p></slot>
        </div>
      </details>
      <hr>
    </template>

**Note**: You can see this complete example in action at [element-details](https://github.com/mdn/web-components-examples/tree/master/element-details) (see it [running live](https://mdn.github.io/web-components-examples/element-details/)). In addition, you can find an explanation at [Using templates and slots](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_templates_and_slots).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comments</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#the-slot-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;slot&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://dom.spec.whatwg.org/#shadow-tree-slots">DOM<br />
<span class="small">The definition of 'Slots' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`slot`

53

79

63

No

40

10

53

53

63

41

10

6.0

`name`

53

79

63

No

40

10

53

53

63

41

10

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/slot" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/slot</a>
