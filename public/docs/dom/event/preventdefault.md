Event.preventDefault()
======================

The [`Event`](../event) interface's `preventDefault()` method tells the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) that if the event does not get explicitly handled, its default action should not be taken as it normally would be. The event continues to propagate as usual, unless one of its event listeners calls [`stopPropagation()`](stoppropagation) or [`stopImmediatePropagation()`](stopimmediatepropagation), either of which terminates propagation at once.

As noted below, calling `preventDefault()` for a non-cancelable event, such as one dispatched via [`EventTarget.dispatchEvent()`](../eventtarget/dispatchevent), without specifying `cancelable: true` has no effect.

Syntax
------

    event.preventDefault();

Examples
--------

### Blocking default click handling

Toggling a checkbox is the default action of clicking on a checkbox. This example demonstrates how to prevent that from happening:

#### JavaScript

    document.querySelector("#id-checkbox").addEventListener("click", function(event) {
             document.getElementById("output-box").innerHTML += "Sorry! <code>preventDefault()</code> won't let you check this!<br>";
             event.preventDefault();
    }, false);

#### HTML

    <p>Please click on the checkbox control.</p>

    <form>
      <label for="id-checkbox">Checkbox:</label>
      <input type="checkbox" id="id-checkbox"/>
    </form>

    <div id="output-box"></div>

#### Result

### Stopping keystrokes from reaching an edit field

The following example demonstrates how invalid text input can be stopped from reaching the input field with `preventDefault()`. Nowadays, you should usually use [native HTML form validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation) instead.

#### HTML

Here's the form:

    <div class="container">
      <p>Please enter your name using lowercase letters only.</p>

      <form>
        <input type="text" id="my-textbox">
      </form>
    </div>

#### CSS

We use a little bit of CSS for the warning box we'll draw when the user presses an invalid key:

    .warning {
      border: 2px solid #f39389;
      border-radius: 2px;
      padding: 10px;
      position: absolute;
      background-color: #fbd8d4;
      color: #3b3c40;
    }

#### JavaScript

And here's the JavaScript code that does the job. First, listen for [`keypress`](../element/keypress_event) events:

    var myTextbox = document.getElementById('my-textbox');
    myTextbox.addEventListener('keypress', checkName, false);

The `checkName()` function, which looks at the pressed key and decides whether to allow it:

    function checkName(evt) {
      var charCode = evt.charCode;
      if (charCode != 0) {
        if (charCode < 97 || charCode > 122) {
          evt.preventDefault();
          displayWarning(
            "Please use lowercase letters only."
            + "\n" + "charCode: " + charCode + "\n"
          );
        }
      }
    }

The `displayWarning()` function presents a notification of a problem. It's not an elegant function but does the job for the purposes of this example:

    var warningTimeout;
    var warningBox = document.createElement("div");
    warningBox.className = "warning";

    function displayWarning(msg) {
      warningBox.innerHTML = msg;

      if (document.body.contains(warningBox)) {
        window.clearTimeout(warningTimeout);
      } else {
        // insert warningBox after myTextbox
        myTextbox.parentNode.insertBefore(warningBox, myTextbox.nextSibling);
      }

      warningTimeout = window.setTimeout(function() {
          warningBox.parentNode.removeChild(warningBox);
          warningTimeout = -1;
        }, 2000);
    }

#### Result

Notes
-----

Calling `preventDefault()` during any stage of event flow cancels the event, meaning that any default action normally taken by the implementation as a result of the event will not occur.

You can use [`Event.cancelable`](cancelable) to check if the event is cancelable. Calling `preventDefault()` for a non-cancelable event has no effect.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-event-preventdefault">DOM<br />
<span class="small">The definition of 'Event.preventDefault()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-Event-preventDefault">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'Event.preventDefault()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`preventDefault`

1

12

1

9

7

1

1

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault</a>
