&lt;input type="button"&gt;
===========================

[`<input>`](../input) elements of type `button` are rendered as simple push buttons, which can be programmed to control custom functionality anywhere on a webpage as required when assigned an event handler function (typically for the `click` event).

**Note**: While `<input>` elements of type `button` are still perfectly valid HTML, the newer [`<button>`](../button) element is now the favored way to create buttons. Given that a [`<button>`](../button)’s label text is inserted between the opening and closing tags, you can include HTML in the label, even images.

<table><tbody><tr class="odd"><td><strong><a href="#value">Value</a></strong></td><td>A <a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMString"><code>DOMString</code></a> used as the button's label</td></tr><tr class="even"><td><strong>Events</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event"><code>click</code></a></td></tr><tr class="odd"><td><strong>Supported common attributes</strong></td><td><a href="../input#attr-type"><code>type</code></a> and <a href="../input#attr-value"><code>value</code></a></td></tr><tr class="even"><td><strong>IDL attributes</strong></td><td><code>value</code></td></tr><tr class="odd"><td><strong>Methods</strong></td><td>None</td></tr></tbody></table>

Value
-----

An `<input type="button">` elements' [`value`](../input#attr-value) attribute contains a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) that is used as the button's label.

    <input type="button" value="Click Me">

If you don't specify a `value`, you get an empty button:

    <input type="button">

Using buttons
-------------

`<input type="button">` elements have no default behavior (their cousins,` <input type="submit">` and `<input type="reset">` are used to submit and reset forms, respectively). To make buttons do anything, you have to write JavaScript code to do the work.

### A simple button

We'll begin by creating a simple button with a `click` event handler that starts our machine (well, it toggles the `value` of the button and the text content of the following paragraph):

    <form>
      <input type="button" value="Start machine">
    </form>
    <p>The machine is stopped.</p>

    const button = document.querySelector('input');
    const paragraph = document.querySelector('p');

    button.addEventListener('click', updateButton);

    function updateButton() {
      if (button.value === 'Start machine') {
        button.value = 'Stop machine';
        paragraph.textContent = 'The machine has started!';
      } else {
        button.value = 'Start machine';
        paragraph.textContent = 'The machine is stopped.';
      }
    }

The script gets a reference to the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) object representing the `<input>` in the DOM, saving this refence in the variable `button`. [`addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) is then used to establish a function that will be run when `click` events occur on the button.

### Adding keyboard shortcuts to buttons

Keyboard shortcuts, also known as access keys and keyboard equivalents, let the user trigger a button using a key or combination of keys on the keyboard. To add a keyboard shortcut to a button — just as you would with any [`<input>`](../input) for which it makes sense — you use the [`accesskey`](../../global_attributes#attr-accesskey) global attribute.

In this example, s is specified as the access key (you'll need to press s plus the particular modifier keys for your browser/OS combination; see [accesskey](../../global_attributes/accesskey) for a useful list of those).

    <form>
      <input type="button" value="Start machine" accesskey="s">
    </form>
    <p>The machine is stopped.</p>

**Note**: The problem with the above example of course is that the user will not know what the access key is! In a real site, you'd have to provide this information in a way that doesn't intefere with the site design (for example by providing an easily accessible link that points to information on what the site accesskeys are).

### Disabling and enabling a button

To disable a button, specify the [`disabled`](../../global_attributes#attr-disabled) global attribute on it, like so:

    <input type="button" value="Disable me" disabled>

You can enable and disable buttons at run time by setting `disabled` to `true` or `false`. In this example our button starts off enabled, but if you press it, it is disabled using `button.disabled = true`. A [`setTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout) function is then used to reset the button back to its enabled state after two seconds.

If the `disabled` attribute isn't specified, the button inherits its `disabled` state from its parent element. This makes it possible to enable and disable groups of elements all at once by enclosing them in a container such as a [`<fieldset>`](../fieldset) element, and then setting `disabled` on the container.

The example below shows this in action. This is very similar to the previous example, except that the `disabled` attribute is set on the `<fieldset>` when the first button is pressed — this causes all three buttons to be disabled until the two second timeout has passed.

**Note**: Firefox will, unlike other browsers, by default, [persist the dynamic disabled state](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing) of a [`<button>`](../button) across page loads. Use the [`autocomplete`](../button#attr-autocomplete) attribute to control this feature.

Validation
----------

Buttons don't participate in constraint validation; they have no real value to be constrained.

Examples
--------

The below example shows a very simple drawing app created using a [`<canvas>`](../canvas) element and some simple CSS and JavaScript (we'll hide the CSS for brevity). The top two controls allow you to choose the color and size of the drawing pen. The button, when clicked, invokes a function that clears the canvas.

    <div class="toolbar">
      <input type="color" aria-label="select pen color">
      <input type="range" min="2" max="50" value="30" aria-label="select pen size"><span class="output">30</span>
      <input type="button" value="Clear canvas">
    </div>

    <canvas class="myCanvas">
      <p>Add suitable fallback here.</p>
    </canvas>

    var canvas = document.querySelector('.myCanvas');
    var width = canvas.width = window.innerWidth;
    var height = canvas.height = window.innerHeight-85;
    var ctx = canvas.getContext('2d');

    ctx.fillStyle = 'rgb(0,0,0)';
    ctx.fillRect(0,0,width,height);

    var colorPicker = document.querySelector('input[type="color"]');
    var sizePicker = document.querySelector('input[type="range"]');
    var output = document.querySelector('.output');
    var clearBtn = document.querySelector('input[type="button"]');

    // covert degrees to radians
    function degToRad(degrees) {
      return degrees * Math.PI / 180;
    };

    // update sizepicker output value

    sizePicker.oninput = function() {
      output.textContent = sizePicker.value;
    }

    // store mouse pointer coordinates, and whether the button is pressed
    var curX;
    var curY;
    var pressed = false;

    // update mouse pointer coordinates
    document.onmousemove = function(e) {
      curX = (window.Event) ? e.pageX : e.clientX + (document.documentElement.scrollLeft ? document.documentElement.scrollLeft : document.body.scrollLeft);
      curY = (window.Event) ? e.pageY : e.clientY + (document.documentElement.scrollTop ? document.documentElement.scrollTop : document.body.scrollTop);
    }

    canvas.onmousedown = function() {
      pressed = true;
    };

    canvas.onmouseup = function() {
      pressed = false;
    }

    clearBtn.onclick = function() {
      ctx.fillStyle = 'rgb(0,0,0)';
      ctx.fillRect(0,0,width,height);
    }

    function draw() {
      if(pressed) {
        ctx.fillStyle = colorPicker.value;
        ctx.beginPath();
        ctx.arc(curX, curY-85, sizePicker.value, degToRad(0), degToRad(360), false);
        ctx.fill();
      }

      requestAnimationFrame(draw);
    }

    draw();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comments</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#button-state-(type=button)">HTML Living Standard<br />
<span class="small">The definition of '&lt;input type="button"&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#button-state-(type=button)">HTML5<br />
<span class="small">The definition of '&lt;input type="button"&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`button`

1

12

1

Yes

Yes

1

Yes

18

4

Yes

Yes

1.0

See also
--------

-   [`<input>`](../input) and the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) interface which implements it.
-   The more modern [`<button>`](../button) element.
-   [Compatibility of CSS properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/button" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/button</a>
