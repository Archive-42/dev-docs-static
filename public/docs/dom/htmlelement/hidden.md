HTMLElement.hidden
==================

The [`HTMLElement`](../htmlelement) property `hidden` is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) which is `true` if the element is hidden; otherwise the value is `false`. This is quite different from using the CSS property [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) to control the visibility of an element. The `hidden` property applies to all presentation modes and should not be used to hide content that is meant to be directly accessible to the user.

Appropriate use cases for `hidden` include:

-   Content that isn't yet relevant but may be needed later
-   Content that was previously needed but is not any longer
-   Content that is reused by other parts of the page in a template-like fashion
-   Creating an offscreen canvas as a drawing buffer

Inappropriate use cases include:

-   Hiding panels in a tabbed dialog box
-   Hiding content in one presentation while intending it to be visible in others

Elements that are not `hidden` must not link to elements which are.

Syntax
------

    isHidden = HTMLElement.hidden;

    HTMLElement.hidden = true | false;

### Value

A Boolean which is `true` if the element is hidden from view; otherwise, the value is `false`.

Example
-------

Here's an example where a hidden block is used to contain a thank you message that is displayed after a user agrees to an unusual request.

### JavaScript

    document.getElementById("okButton")
            .addEventListener("click", function() {
      document.getElementById("welcome").hidden = true;
      document.getElementById("awesome").hidden = false;
    }, false);

This code sets up a handler for the welcome panel's "OK" button that hides the welcome panel and makes the follow-up panel—with the curious name "awesome"—visible in its place.

### HTML

The HTML for the two boxes are shown here.

#### The welcome panel

    <div id="welcome" class="panel">
      <h1>Welcome to Foobar.com!</h1>
      <p>By clicking "OK" you agree to be awesome every day!</p>
      <button class="button" id="okButton">OK</button>
    </div>

This HTML creates a panel (in a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) block) that welcomes the user to a site and tells them what they're agreeing to by clicking the OK button.

#### The follow-up panel

Once the user clicks the "OK" button in the welcome panel, the JavaScript code swaps the two panels by changing their respective values for `hidden`. The follow-up panel looks like this in HTML:

    <div id="awesome" class="panel" hidden>
      <h1>Thanks!</h1>
      <p>Thank you <strong>so</strong> much for agreeing to be
      awesome today! Now get out there and do awesome things
      awesomely to make the world more awesome!</p>
    </div>

### CSS

The content is styled using the CSS below.

    .panel {
      font: 16px "Open Sans", Helvetica, Arial, sans-serif;
      border: 1px solid #22d;
      padding: 12px;
      width: 500px;
      text-align: center;
    }

    .button {
      font: 22px "Open Sans", Helvetica, Arial, sans-serif;
      padding: 5px 36px;
    }

    h1 {
      margin-top: 0;
      font-size: 175%;
    }

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dom-hidden">HTML Living Standard<br />
<span class="small">The definition of 'HTMLElement.hidden' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#the-hidden-attribute">HTML 5.1<br />
<span class="small">The definition of 'HTMLElement.hidden' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/editing.html#the-hidden-attribute">HTML5<br />
<span class="small">The definition of 'HTMLElement.hidden' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`hidden`

6

12

1

11

11.6

5.1

≤37

18

4

12

5

1.0

See also
--------

-   [`hidden`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-hidden) attribute
-   [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/hidden" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/hidden</a>
