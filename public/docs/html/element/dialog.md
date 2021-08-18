&lt;dialog&gt;: The Dialog element
==================================

The `<dialog>` represents a dialog box or other interactive component, such as a dismissible alert, inspector, or subwindow.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines#sectioning_roots">sectioning root</a></td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a></td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a></td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/dialog_role">dialog</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>alertdialog</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement"><code>HTMLDialogElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

The `tabindex` attribute must not be used on the `<dialog>` element.

`open`  
Indicates that the dialog is active and can be interacted with. When the `open` attribute is not set, the dialog *shouldn't* be shown to the user.

Usage notes
-----------

-   [`<form>`](form) elements can close a dialog if they have the attribute `method="dialog"`. When such a form is submitted, the dialog closes with its [`returnValue`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement/returnValue) property set to the `value` of the button that was used to submit the form.
-   The [`::backdrop`](https://developer.mozilla.org/en-US/docs/Web/CSS/::backdrop) CSS pseudo-element can be used to style behind a `<dialog>` element when the dialog is displayed with [`HTMLDialogElement.showModal()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement/showModal). For example, to dim unreachable content behind the modal dialog.

Examples
--------

### Simple example

    <dialog open>
      <p>Greetings, one and all!</p>
    </dialog>

### Advanced example

This example opens a pop-up dialog box that contains a form, when the "Update details" button is clicked.

#### HTML

    <!-- Simple pop-up dialog box containing a form -->
    <dialog id="favDialog">
      <form method="dialog">
        <p><label>Favorite animal:
          <select>
            <option></option>
            <option>Brine shrimp</option>
            <option>Red panda</option>
            <option>Spider monkey</option>
          </select>
        </label></p>
        <menu>
          <button value="cancel">Cancel</button>
          <button id="confirmBtn" value="default">Confirm</button>
        </menu>
      </form>
    </dialog>

    <menu>
      <button id="updateDetails">Update details</button>
    </menu>

    <output aria-live="polite"></output>

#### JavaScript

    var updateButton = document.getElementById('updateDetails');
    var favDialog = document.getElementById('favDialog');
    var outputBox = document.querySelector('output');
    var selectEl = document.querySelector('select');
    var confirmBtn = document.getElementById('confirmBtn');

    // "Update details" button opens the <dialog> modally
    updateButton.addEventListener('click', function onOpen() {
      if (typeof favDialog.showModal === "function") {
        favDialog.showModal();
      } else {
        alert("The <dialog> API is not supported by this browser");
      }
    });
    // "Favorite animal" input sets the value of the submit button
    selectEl.addEventListener('change', function onSelect(e) {
      confirmBtn.value = selectEl.value;
    });
    // "Confirm" button of form triggers "close" on dialog because of [method="dialog"]
    favDialog.addEventListener('close', function onClose() {
      outputBox.value = favDialog.returnValue + " button clicked - " + (new Date()).toString();
    });

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#the-dialog-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;dialog&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/interactive-elements.html#the-dialog-element">HTML 5.2<br />
<span class="small">The definition of '&lt;dialog&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`dialog`

37

79

53

See [bug 840640](https://bugzil.la/840640).

No

24

No

37

37

53

See [bug 840640](https://bugzil.la/840640).

24

No

3.0

`open`

37

79

53

See [bug 840640](https://bugzil.la/840640).

No

24

No

37

37

53

See [bug 840640](https://bugzil.la/840640).

24

No

3.0

Polyfill
--------

Include this polyfill to provide support for browsers without `<dialog>` element.

[dialog-polyfill](https://github.com/GoogleChrome/dialog-polyfill)

See also
--------

-   The [`close`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement/close_event) event
-   The [`cancel`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement/cancel_event) event
-   [HTML forms guide](https://developer.mozilla.org/en-US/docs/Learn/Forms).
-   The [`::backdrop`](https://developer.mozilla.org/en-US/docs/Web/CSS/::backdrop) pseudo-element

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog</a>
