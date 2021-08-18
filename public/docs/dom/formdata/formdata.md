FormData()
==========

The `FormData()` constructor creates a new [`FormData`](../formdata) object.

**Note**: This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var formData = new FormData(form)

### Parameters

 `form `<span class="badge inline optional">Optional</span>   
An HTML [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element — when specified, the [`FormData`](../formdata) object will be populated with the form's current keys/values using the name property of each element for the keys and their submitted value for the values. It will also encode file input content.

Example
-------

The following line creates an empty `FormData` object:

    var formData = new FormData(); // Currently empty

You could add a key/value pair to this using [`FormData.append`](append):

    formData.append('username', 'Chris');

Or you can specify the optional `form` argument when creating the `FormData` object, to prepopulate it with values from the specified form:

    <form id="myForm" name="myForm">
      <div>
        <label for="username">Enter name:</label>
        <input type="text" id="username" name="username">
      </div>
      <div>
        <label for="useracc">Enter account number:</label>
        <input type="text" id="useracc" name="useracc">
      </div>
      <div>
        <label for="userfile">Upload file:</label>
        <input type="file" id="userfile" name="userfile">
      </div>
      <input type="submit" value="Submit!">
    </form>

**Note**: Only successful form controls are included in a FormData object, i.e. those with a name, not disabled and checked (radio buttons and checkboxes) or selected (one or more options within a select).

    let myForm = document.getElementById('myForm');
    let formData = new FormData(myForm);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#dom-formdata">XMLHttpRequest<br />
<span class="small">The definition of 'FormData()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`FormData`

7

12

4

10

12

5

≤37

18

4

12

5

1.0

See also
--------

-   [`XMLHTTPRequest`](../xmlhttprequest)
-   [Using XMLHttpRequest](../xmlhttprequest/using_xmlhttprequest)
-   [Using FormData objects](using_formdata_objects)
-   [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FormData/FormData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FormData/FormData</a>
