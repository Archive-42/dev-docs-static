HTMLDialogElement
=================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `HTMLDialogElement` interface provides methods to manipulate [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog) elements. It inherits properties and methods from the [`HTMLElement`](htmlelement) interface.

Properties
----------

*Inherits properties from its parent, [`HTMLElement`](htmlelement).*

[`HTMLDialogElement.open`](htmldialogelement/open)  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) reflecting the [`open`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog#attr-open) HTML attribute, indicating whether the dialog is available for interaction.

[`HTMLDialogElement.returnValue`](htmldialogelement/returnvalue)  
A [`DOMString`](domstring) that sets or returns the return value for the dialog.

Methods
-------

*Inherits methods from its parent, [`HTMLElement`](htmlelement).*

[`HTMLDialogElement.close()`](htmldialogelement/close)  
Closes the dialog. An optional [`DOMString`](domstring) may be passed as an argument, updating the `returnValue` of the dialog.

[`HTMLDialogElement.show()`](htmldialogelement/show)  
Displays the dialog modelessly, i.e. still allowing interaction with content outside of the dialog.

[`HTMLDialogElement.showModal()`](htmldialogelement/showmodal)  
Displays the dialog as a modal, over the top of any other dialogs that might be present. Interaction outside the dialog is blocked.

Events
------

[`close`](htmldialogelement/close_event)  
Fired when the dialog is closed.  
Also available via the [`onclose`](globaleventhandlers/onclose) property.

Examples
--------

The following example shows a simple button that, when clicked, opens a [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog) containing a form via the [`HTMLDialogElement.showModal()`](htmldialogelement/showmodal) function. From there you can click the *Cancel* button to close the dialog (via the [`HTMLDialogElement.close()`](htmldialogelement/close) function), or submit the form via the submit button.

      <!-- Simple pop-up dialog box, containing a form -->
      <dialog id="favDialog">
        <form method="dialog">
          <section>
            <p><label for="favAnimal">Favorite animal:</label>
            <select id="favAnimal" name="favAnimal">
              <option></option>
              <option>Brine shrimp</option>
              <option>Red panda</option>
              <option>Spider monkey</option>
            </select></p>
          </section>
          <menu>
            <button id="cancel" type="reset">Cancel</button>
            <button type="submit">Confirm</button>
          </menu>
        </form>
      </dialog>

      <menu>
        <button id="updateDetails">Update details</button>
      </menu>

      <script>
        (function() {
          var updateButton = document.getElementById('updateDetails');
          var cancelButton = document.getElementById('cancel');
          var dialog = document.getElementById('favDialog');
          dialog.returnValue = 'favAnimal';

          function openCheck(dialog) {
            if(dialog.open) {
              console.log('Dialog open');
            } else {
              console.log('Dialog closed');
            }
          }

          // Update button opens a modal dialog
          updateButton.addEventListener('click', function() {
            dialog.showModal();
            openCheck(dialog);
          });

          // Form cancel button closes the dialog box
          cancelButton.addEventListener('click', function() {
            dialog.close('animalNotChosen');
            openCheck(dialog);
          });

        })();
      </script>

**Note**: You can find this example on GitHub as [htmldialogelement-basic](https://github.com/mdn/dom-examples/blob/master/htmldialogelement-basic/index.html) ([see it live also](https://mdn.github.io/dom-examples/htmldialogelement-basic/)).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmldialogelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLDialogElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/interactive-elements.html#the-dialog-element">HTML 5.2<br />
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

`HTMLDialogElement`

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

`cancel_event`

Yes

79

78

No

?

No

No

No

No

No

No

No

`close`

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

`close_event`

Yes

79

No

No

?

No

No

No

No

No

No

No

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

`show`

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

`showModal`

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

See also
--------

-   The HTML element implementing this interface: [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement</a>
