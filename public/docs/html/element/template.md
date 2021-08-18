&lt;template&gt;: The Content Template element
==============================================

The `<template>` is a mechanism for holding [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML) that is not to be rendered immediately when a page is loaded but may be instantiated subsequently during runtime using JavaScript.

Think of a template as a content fragment that is being stored for subsequent use in the document. While the parser does process the contents of the `<template>` element while loading the page, it does so only to ensure that those contents are valid; the element's contents are not rendered, however.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#metadata_content">Metadata content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#script-supporting_elements">script-supporting element</a></td></tr><tr class="even"><td>Permitted content</td><td>No restrictions</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#metadata_content">metadata content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, or <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#script-supporting_elements">script-supporting elements</a>. Also allowed as a child of a <a href="colgroup"><code>&lt;colgroup&gt;</code></a> element that does <em>not</em> have a <a href="colgroup#attr-span"><code>span</code></a> attribute.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTemplateElement"><code>HTMLTemplateElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

However, the [`HTMLTemplateElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTemplateElement) has a [`content`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTemplateElement/content) property, which is a read-only [`DocumentFragment`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment) containing the DOM subtree which the template represents. Note that directly using the value of the [`content`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTemplateElement/content) could lead to unexpected behavior, see [Avoiding DocumentFragment pitfall](#avoiding_documentfragment_pitfall) section below.

Examples
--------

First we start with the HTML portion of the example.

    <table id="producttable">
      <thead>
        <tr>
          <td>UPC_Code</td>
          <td>Product_Name</td>
        </tr>
      </thead>
      <tbody>
        <!-- existing data could optionally be included here -->
      </tbody>
    </table>

    <template id="productrow">
      <tr>
        <td class="record"></td>
        <td></td>
      </tr>
    </template>

First, we have a table into which we will later insert content using JavaScript code. Then comes the template, which describes the structure of an HTML fragment representing a single table row.

Now that the table has been created and the template defined, we use JavaScript to insert rows into the table, with each row being constructed using the template as its basis.

    // Test to see if the browser supports the HTML template element by checking
    // for the presence of the template element's content attribute.
    if ('content' in document.createElement('template')) {

        // Instantiate the table with the existing HTML tbody
        // and the row with the template
        var tbody = document.querySelector("tbody");
        var template = document.querySelector('#productrow');

        // Clone the new row and insert it into the table
        var clone = template.content.cloneNode(true);
        var td = clone.querySelectorAll("td");
        td[0].textContent = "1235646565";
        td[1].textContent = "Stuff";

        tbody.appendChild(clone);

        // Clone the new row and insert it into the table
        var clone2 = template.content.cloneNode(true);
        td = clone2.querySelectorAll("td");
        td[0].textContent = "0384928528";
        td[1].textContent = "Acme Kidney Beans 2";

        tbody.appendChild(clone2);

    } else {
      // Find another way to add the rows to the table because
      // the HTML template element is not supported.
    }

The result is the original HTML table, with two new rows appended to it via JavaScript:

Avoiding DocumentFragment pitfall
---------------------------------

A [`DocumentFragment`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment) is not a valid target for various events, as such it is often preferable to clone or refer to the elements within it.

Consider the following HTML and JavaScript:

### HTML

    <div id="container"></div>

    <template id="template">
      <div>Click me</div>
    </template>

### JavaScript

    const container = document.getElementById("container");
    const template = document.getElementById("template");

    function clickHandler(event) {
      alert("Clicked a div");
    }

    const firstClone = template.content.cloneNode(true);
    firstClone.addEventListener("click", clickHandler);
    container.appendChild(firstClone);

    const secondClone = template.content.firstElementChild.cloneNode(true);
    secondClone.addEventListener("click", clickHandler);
    container.appendChild(secondClone);

### Result

`firstClone` is a DocumentFragment instance, so while it gets appended inside the container as expected, clicking on it does not trigger the click event. `secondClone` is an [HTMLDivElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDivElement) instance, clicking on it works as one would expect.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#the-template-element">HTML Living Standard<br />
<span class="small">The definition of 'template element' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/semantics-scripting.html#the-template-element">HTML5<br />
<span class="small">The definition of 'template element' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`template`

26

13

22

No

15

8

Yes

26

22

?

8

1.5

See also
--------

-   Web components: [`<slot>`](slot) (and historical: [`<shadow>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/shadow))
-   [Using templates and slots](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_templates_and_slots)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template</a>
