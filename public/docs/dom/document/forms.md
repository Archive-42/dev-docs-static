# Document.forms

The `forms` read-only property of the [`Document`](../document) interface returns an [`HTMLCollection`](../htmlcollection) listing all the [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) elements contained in the document.

**Note:** Similarly, you can access a list of a form's component user input elements using the [`HTMLFormElement.elements`](../htmlformelement/elements) property.

## Syntax

    collection = document.forms;

### Value

An [`HTMLCollection`](../htmlcollection) object listing all of the document's forms. Each item in the collection is a [`HTMLFormElement`](../htmlformelement) representing a single `<form>` element.

If the document has no forms, the returned collection is empty, with a length of zero.

## Examples

### Getting form information

    <!DOCTYPE html>
    <html lang="en">

    <head>
    <title>document.forms example</title>
    </head>

    <body>

    <form id="robby">
      <input type="button" onclick="alert(document.forms[0].id);" value="robby's form" />
    </form>

    <form id="dave">
      <input type="button" onclick="alert(document.forms[1].id);" value="dave's form" />
    </form>

    <form id="paul">
      <input type="button" onclick="alert(document.forms[2].id);" value="paul's form" />
    </form>

    </body>
    </html>

### Getting an element from within a form

    var selectForm = document.forms[index];
    var selectFormElement = document.forms[index].elements[index];

### Named form access

    <!DOCTYPE html>
    <html lang="en">
    <head>
      <title>document.forms example</title>
    </head>

    <body>

    <form name="login">
      <input name="email" type="email">
      <input name="password" type="password">
      <button type="submit">Log in</button>
    </form>

    <script>
      var loginForm = document.forms.login; // Or document.forms['login']
      loginForm.elements.email.placeholder = 'test@example.com';
      loginForm.elements.password.placeholder = 'password';
    </script>
    </body>
    </html>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-document-forms">HTML Living Standard<br />
<span class="small">The definition of 'Document.forms' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-1689064">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'Document.forms' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`forms`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

## See also

- [HTML forms](https://developer.mozilla.org/en-US/docs/Learn/Forms)
- [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) and the [`HTMLFormElement`](../htmlformelement) interface

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/forms" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/forms</a>
