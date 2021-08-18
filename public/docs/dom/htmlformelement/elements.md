HTMLFormElement.elements
========================

The [`HTMLFormElement`](../htmlformelement) property `elements` returns an [`HTMLFormControlsCollection`](../htmlformcontrolscollection) listing all the form controls contained in the [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element. Independently, you can obtain just the number of form controls using the [`length`](length) property.

You can access a particular form control in the returned collection by using either an index or the element's [`name`](../index) or [`id`](../element/id).

Prior to HTML 5, the returned object was an [`HTMLCollection`](../htmlcollection), on which `HTMLFormControlsCollection` is based.

**Note:** Similarly, you can get a list of all of the forms contained within a given document using the document's [`forms`](../document/forms) property.

Syntax
------

    nodeList = HTMLFormElement.elements

### Value

An [`HTMLFormControlsCollection`](../htmlformcontrolscollection) containing all non-image controls in the form. This is a live collection; if form controls are added to or removed from the form, this collection will update to reflect the change.

The form controls in the returned collection are in the same order in which they appear in the form by following a preorder, depth-first traversal of the tree. This is called **tree order**.

The elements included by `HTMLFormElement.elements` and `HTMLFormElement.length` are the following:

-   [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)
-   [`<fieldset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset)
-   [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) (with the exception that any whose [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type) is `"image"` are omitted for historical reasons)
-   [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object)
-   [`<output>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/output)
-   [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)
-   [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)

No other elements are included in the list returned by `elements`, which makes it an excellent way to get at the elements most important when processing forms.

Example
-------

### Quick syntax example

In this example, we see how to obtain the list of form controls as well as how to access its members by index and by name or ID.

    <form id="my-form">
      <input type="text" name="username">
      <input type="text" name="full-name">
      <input type="password" name="password">
    </form>

    var inputs = document.getElementById("my-form").elements;
    var inputByIndex = inputs[0];
    var inputByName = inputs["username"];

### Accessing form controls

This example gets the form's element list, then iterates over the list, looking for [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) elements of type `"text"` so that some form of processing can be performed on them.

    var inputs = document.getElementById("my-form").elements;

    // Iterate over the form controls
    for (i = 0; i < inputs.length; i++) {
      if (inputs[i].nodeName === "INPUT" && inputs[i].type === "text") {
        // Update text input
        inputs[i].value.toLocaleUpperCase();
      }
    }

### Disabling form controls

    var inputs = document.getElementById("my-form").elements;

    // Iterate over the form controls
    for (i = 0; i < inputs.length; i++) {
      // Disable all form controls
      inputs[i].setAttribute("disabled", "");
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-form-elements">HTML Living Standard<br />
<span class="small">The definition of 'HTMLFormElement.elements' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-76728479">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLFormElement.elements' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`elements`

1

12

1

5.5

8

3

1

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements</a>
