# HTMLFormElement.method

The `HTMLFormElement.method` property represents the [HTTP](https://developer.mozilla.org/en-US/docs/Glossary/HTTP) method used to submit the [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form).

Unless explicitly specified, the default method is 'get'.

## Syntax

    var string = form.method;
    form.method = string;

## Example

    document.forms['myform'].method = 'post';

    const formElement = document.createElement("form"); // Create a form
    document.body.appendChild(formElement);
    console.log(formElement.method); // 'get'

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-fs-method">HTML Living Standard<br />
<span class="small">The definition of 'HTMLFormElement: method' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/method" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/method</a>
