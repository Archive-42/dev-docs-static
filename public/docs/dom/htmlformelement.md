HTMLFormElement
===============

The `HTMLFormElement` interface represents a [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element in the DOM. It allows access to—and, in some cases, modification of—aspects of the form, as well as access to its component elements.

Properties
----------

*This interface also inherits properties from its parent, [`HTMLElement`](htmlelement).*

 [`HTMLFormElement.elements`](htmlformelement/elements) <span class="badge inline readonly">Read only </span>   
A [`HTMLFormControlsCollection`](htmlformcontrolscollection) holding all form controls belonging to this form element.

 [`HTMLFormElement.length`](htmlformelement/length)<span class="badge inline readonly">Read only </span>   
A `long` reflecting the number of controls in the form.

[`HTMLFormElement.name`](htmlformelement/name)  
A [`DOMString`](domstring) reflecting the value of the form's [`name`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-name) HTML attribute, containing the name of the form.

[`HTMLFormElement.method`](htmlformelement/method)  
A [`DOMString`](domstring) reflecting the value of the form's [`method`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-method) HTML attribute, indicating the HTTP method used to submit the form. Only specified values can be set.

[`HTMLFormElement.target`](htmlformelement/target)  
A [`DOMString`](domstring) reflecting the value of the form's [`target`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-target) HTML attribute, indicating where to display the results received from submitting the form.

[`HTMLFormElement.action`](htmlformelement/action)  
A [`DOMString`](domstring) reflecting the value of the form's [`action`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-action) HTML attribute, containing the URI of a program that processes the information submitted by the form.

 [`HTMLFormElement.encoding`](htmlformelement/encoding) or [`HTMLFormElement.enctype`](htmlformelement/enctype)   
A [`DOMString`](domstring) reflecting the value of the form's [`enctype`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-enctype) HTML attribute, indicating the type of content that is used to transmit the form to the server. Only specified values can be set. The two properties are synonyms.

[`HTMLFormElement.acceptCharset`](htmlformelement/acceptcharset)  
A [`DOMString`](domstring) reflecting the value of the form's [`accept-charset`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-accept-charset) HTML attribute, representing the character encoding that the server accepts.

<span class="page-not-created">`HTMLFormElement.autocomplete`</span>  
A [`DOMString`](domstring) reflecting the value of the form's [`autocomplete`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-autocomplete) HTML attribute, indicating whether the controls in this form can have their values automatically populated by the browser.

<span class="page-not-created">`HTMLFormElement.noValidate`</span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) reflecting the value of the form's [`novalidate`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-novalidate) HTML attribute, indicating whether the form should not be validated.

Named inputs are added to their owner form instance as properties, and can overwrite native properties if they share the same name (e.g. a form with an input named `action` will have its `action` property return that input instead of the form's [`action`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-action) HTML attribute).

Methods
-------

*This interface also inherits methods from its parent, [`HTMLElement`](htmlelement).*

<span class="page-not-created">`checkValidity()`</span>  
Returns `true` if the element's child controls are subject to [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation) and satisfy those constraints; returns `false` if some controls do not satisfy their constraints. Fires an event named [`invalid`](htmlinputelement/invalid_event) at any control that does not satisfy its constraints; such controls are considered invalid if the event is not canceled. It is up to the programmer to decide how to respond to `false`.

[`reportValidity()`](htmlformelement/reportvalidity)  
Returns `true` if the element's child controls satisfy their [validation constraints](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). When `false` is returned, cancelable [`invalid`](htmlinputelement/invalid_event) events are fired for each invalid child and validation problems are reported to the user.

[`requestSubmit()`](htmlformelement/requestsubmit)  
Requests that the form be submitted using the specified submit button and its corresponding configuration.

[`reset()`](htmlformelement/reset)  
Resets the form to its initial state.

[`submit()`](htmlformelement/submit)  
Submits the form to the server.

### Deprecated methods

 <span class="page-not-created">`HTMLFormElement.requestAutocomplete()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Triggers a native browser interface to assist the user in completing the fields which have an [autofill field name](https://html.spec.whatwg.org/#autofill-field-name) value that is not `off` or `on`. The form will receive an event once the user has finished with the interface, the event will either be `autocomplete` when the fields have been filled or `autocompleteerror` when there was a problem.

Events
------

Listen to these events using `addEventListener()`, or by assigning an event listener to the `oneventname` property of this interface.

[`formdata`](htmlformelement/formdata_event)  
The `formdata` event fires after the entry list representing the form's data is constructed.  
Also available via the [`onformdata`](globaleventhandlers/onformdata) property.

[`reset`](htmlformelement/reset_event)  
The `reset` event fires when a form is reset.  
Also available via the [`onreset`](globaleventhandlers/onreset) property.

[`submit`](htmlformelement/submit_event)  
The `submit` event fires when a form is submitted.  
Also available via the [`onsubmit`](globaleventhandlers/onsubmit) property.

Usage notes
-----------

### Obtaining a form element object

To obtain an `HTMLFormElement` object, you can use a [CSS selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors) with [`querySelector()`](parentnode/queryselector), or you can get a list of all of the forms in the document using its [`forms`](document/forms) property.

[`Document.forms`](document/forms) returns an array of `HTMLFormElement` objects listing each of the forms on the page. You can then use any of the following syntaxes to get an individual form:

`document.forms[index]`  
Returns the form at the specified `index` into the array of forms.

`document.forms[id]`  
Returns the form whose ID is `id`.

`document.forms[name]`  
Returns the form whose [`name`](index) attribute's value is `name`.

### Accessing the form's elements

You can access the list of the form's data-containing elements by examining the form's [`elements`](htmlformelement/elements) property. This returns an [`HTMLFormControlsCollection`](htmlformcontrolscollection) listing all of the form's user data entry elements, both those which are descendants of the `<form>` and those which are made members of the form using their `form` attributes.

You can also get the form's element by using its `name` attribute as a key of the `form`, but using `elements` is a better approach—it contains *only* the form's elements, and it cannot be mixed with other attributes of the `form`.

### Issues with Naming Elements

Some names will interfere with JavaScript access to the form’s properties and elements.

For example:

-   `<input name="id">` will take precedence over `<form id="…">`. This means that `form.id` will not refer to the form’s id, but to the element whose name is "`id`". This will be the case with any other form properties, such as `<input name="action">` or `<input name="post">`.
-   `<input name="elements">` will render the form’s `elements` collection inaccessible. The reference `form.elements` will now refer to the individual element.

To avoid such problems with element names:

-   *Always* use the `elements` collection to avoid ambiguity between an element name and a form property.
-   *Never* use "`elements`" as an element name.

If you are not using JavaScript, this will not cause a problem.

### Elements that are considered form controls

The elements included by `HTMLFormElement.elements` and `HTMLFormElement.length` are the following:

-   [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)
-   [`<fieldset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset)
-   [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) (with the exception that any whose [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type) is `"image"` are omitted for historical reasons)
-   [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object)
-   [`<output>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/output)
-   [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)
-   [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)

No other elements are included in the list returned by `elements`, which makes it an excellent way to get at the elements most important when processing forms.

Examples
--------

Creating a new form element, modifying its attributes, then submitting it:

    const f = document.createElement("form"); // Create a form
    document.body.appendChild(f);             // Add it to the document body
    f.action = "/cgi-bin/some.cgi";           // Add action and method attributes
    f.method = "POST";
    f.submit();                               // Call the form's submit() method

Extract information from a `<form>` element and set some of its attributes:

    <form name="formA" action="/cgi-bin/test" method="post">
     <p>Press "Info" for form details, or "Set" to change those details.</p>
     <p>
      <button type="button" onclick="getFormInfo();">Info</button>
      <button type="button" onclick="setFormInfo(this.form);">Set</button>
      <button type="reset">Reset</button>
     </p>

     <textarea id="form-info" rows="15" cols="20"></textarea>
    </form>

    <script>
      function getFormInfo(){
        // Get a reference to the form via its name
        var f = document.forms["formA"];
        // The form properties we're interested in
        var properties = [ 'elements', 'length', 'name', 'charset', 'action', 'acceptCharset', 'action', 'enctype', 'method', 'target' ];
        // Iterate over the properties, turning them into a string that we can display to the user
        var info = properties.map(function(property) { return property + ": " + f[property] }).join("\n");

        // Set the form's <textarea> to display the form's properties
        document.forms["formA"].elements['form-info'].value = info; // document.forms["formA"]['form-info'].value would also work
      }

      function setFormInfo(f){ // Argument should be a form element reference.
        f.action = "a-different-url.cgi";
        f.name   = "a-different-name";
      }
    </script>

Submit a `<form>` into a new window:

    <!doctype html>
    <html>
    <head>
    <meta charset="utf-8">
    <title>Example new-window form submission</title>
    </head>
    <body>

    <form action="test.php" target="_blank">
      <p><label>First name: <input type="text" name="firstname"></label></p>
      <p><label>Last name: <input type="text" name="lastname"></label></p>
      <p><label><input type="password" name="pwd"></label></p>

      <fieldset>
       <legend>Pet preference</legend>

        <p><label><input type="radio" name="pet" value="cat"> Cat</label></p>
        <p><label><input type="radio" name="pet" value="dog"> Dog</label></p>
      </fieldset>

      <fieldset>
        <legend>Owned vehicles</legend>

        <p><label><input type="checkbox" name="vehicle" value="Bike">I have a bike</label></p>
        <p><label><input type="checkbox" name="vehicle" value="Car">I have a car</label></p>
      </fieldset>

      <p><button>Submit</button></p>
    </form>

    </body>
    </html>

### Submitting forms and uploading files using XMLHttpRequest

If you want to know how to serialize and submit a form using the [`XMLHttpRequest`](xmlhttprequest) API, please read [this paragraph](xmlhttprequest/using_xmlhttprequest#submitting_forms_and_uploading_files).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlformelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLFormElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>The following method has been added: <code>requestAutocomplete()</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#htmlformelement">HTML5<br />
<span class="small">The definition of 'HTMLFormElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The elements properties returns an <a href="htmlformcontrolscollection"><code>HTMLFormControlsCollection</code></a> instead of a raw <a href="htmlcollection"><code>HTMLCollection</code></a>. This is mainly a technical change. The following method has been added: <code>checkValidity()</code>. The following properties have been added: <code>autocomplete</code>, <code>noValidate</code>, and <code>encoding</code>.</td></tr></tbody></table>

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

`HTMLFormElement`

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

`acceptCharset`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`action`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`autocomplete`

14

12

4

10

15

6

≤37

18

4

14

6

1.0

`checkValidity`

4

12

4

10

≤12.1

5

≤37

18

4

≤12.1

4

1.0

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

`encoding`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`enctype`

1

12

1

6

≤12.1

3

1

18

4

≤12.1

1

1.0

`formdata_event`

77

79

72

No

64

No

77

77

No

55

No

12.0

`length`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`method`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`name`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`noValidate`

4

12

4

10

≤12.1

5

≤37

18

4

≤12.1

4

1.0

`reportValidity`

40

17

49

No

27

10.1

40

40

49

27

10.3

4.0

`requestSubmit`

76

79

75

No

63

No

76

76

79

54

No

12.0

`reset`

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

`reset_event`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`submit`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`submit_event`

1

12

1

9

8

3

1

18

4

10.1

1

1.0

`target`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

See also
--------

-   The HTML element implementing this interface: [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement</a>
