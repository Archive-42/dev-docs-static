# HTMLDialogElement.returnValue

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `returnValue` property of the [`HTMLDialogElement`](../htmldialogelement) interface gets or sets the return value for the `<dialog>`, usually to indicate which button the user pressed to close it.

## Syntax

    dialogInstance.returnValue = 'myReturnValue';
    var myReturnValue = dialogInstance.returnValue;

### Value

A [`DOMString`](../domstring) representing the `returnValue` of the dialog.

## Examples

The following example displays a button to open a [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog) containing a form via the `showModal()` method. From there, either button will close the dialog.

      <!-- Simple pop-up dialog box containing a form -->
      <dialog id="favDialog">
        <form method="dialog">
          <p><label>Favorite animal:
            <select name="favAnimal" required>
              <option></option>
              <option>Brine shrimp</option>
              <option>Red panda</option>
              <option>Spider monkey</option>
            </select>
          </label></p>
          <menu>
            <button>Cancel</button>
            <button>Confirm</button>
          </menu>
        </form>
      </dialog>

      <menu>
        <button id="updateDetails">Update details</button>
      </menu>

      <script>
        (function() {
          var updateButton = document.getElementById('updateDetails');
          var dialog = document.getElementById('favDialog');
          dialog.returnValue = 'favAnimal';

          function openCheck(dialog) {
            if (dialog.open) {
              console.log('Dialog open');
            } else {
              console.log('Dialog closed');
            }
          }

          function handleUserInput(returnValue) {
            if (returnValue === 'Cancel' || returnValue == null) {
              // User canceled the dialog, do nothing
            } else if (returnValue === 'Confirm') {
              // User chose a favorite animal, do something with it
            }
          }

          // “Update details” button opens the <dialog> modally
          updateButton.addEventListener('click', function() {
            dialog.showModal();
            openCheck(dialog);
            handleUserInput(dialog.returnValue);
          });
        })();
      </script>

**Note**: You can find this example on GitHub as [htmldialogelement-basic](https://github.com/mdn/dom-examples/blob/master/htmldialogelement-basic/index.html) ([see it live also](https://mdn.github.io/dom-examples/htmldialogelement-basic/)).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#dom-dialog-returnvalue">HTML Living Standard<br />
<span class="small">The definition of 'returnvalue' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/interactive-elements.html#dom-htmldialogelement-returnvalue">HTML 5.1<br />
<span class="small">The definition of 'returnvalue' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

## Browser compatibility

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

`returnValue`

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

## See also

- The HTML element implementing this interface: [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement/returnValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement/returnValue</a>
