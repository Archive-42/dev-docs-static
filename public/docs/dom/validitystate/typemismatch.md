ValidityState.typeMismatch
==========================

**Draft**

This page is not complete.

The read-only `typeMismatch` property of a `ValidityState` object indicates if the value of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), after having been edited by the user, does not conform to the constraints set by the element's `type` attribute.

If the `type` attribute expects specific strings, such as the [email](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/email) and [url](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/url) types and the value don't doesn't conform to the constraints set by the type, the `typeMismatch` property will be true.

The [email](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/email) input type expects one or more valid email addresses, depending on whether the `multiple` attribute is present. A valid email address includes an email prefix and a domain, with or without a top level domain. If the value of the email input is not an empty string, a single valid e-mail address, or one or more comma separated email address if the `multiple` attribute is present, there is a `typeMismatch`.

The [url](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/url) input type expects one or more valid email URLs, depending on whether the `multiple` attribute is present. A valid URL includes a protocol, optionally with an IP address, or an optional subdomain, domain, and top level domain combination. If the value of the URL input is not an empty string, a single valid URL, or one or more comma separated URLS if the `multiple` attribute is present, there is a `typeMismatch`.

<table><caption> <code>type</code> attribute conformance</caption><thead><tr class="header"><th>Input type</th><th>Value</th><th>Expected value</th></tr></thead><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/email">email</a></td><td><code>x@y</code> or <code>x@y.z</code></td><td>email address, with or without <a href="https://developer.mozilla.org/en-US/docs/Glossary/TLD">TLD</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/url">url</a></td><td><code>x:</code> or <code>x://y.z</code></td><td>protocol or full URL with protocol</td></tr></tbody></table>

Examples
--------

Given the following:

    <p>
     <label>
        Enter an email address:
        <input type="email" value="example.com"/>
     </label>
    </p>
    <p>
     <label>
         Enter a URL:
         <input type="url" value="example.com"/>
      </label>
    </p>

    input:invalid {
      border: red solid 3px;
    }

The above each produce a `typeMismatch` because the email address is just a domain and the URL has no protocol

The `typeMismatch` occurs when there is a disconnect between the `value` expected via the `type` attribute and the data that is actually present. The `typeMismatch` is only one of the many possible errors and is only relevant for the [email](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/email) and [url](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/url) types. When the value provided doesn't match the expected value based on the type for other input types, you get different errors. For example, if the [number](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/number) input value is not a floating point number, the `badInput` is `true`. If the email is `required` but is empty, the <span class="page-not-created">`valueMissing`</span> will be `true`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/constraints.html#dom-validitystate-typemismatch">HTML Living Standard<br />
<span class="small">The definition of 'ValidityState.typeMismatch' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#dom-validitystate-typemismatch">HTML 5.1<br />
<span class="small">The definition of 'ValidityState.typeMismatch' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/forms.html#dom-validitystate-typemismatch">HTML5<br />
<span class="small">The definition of 'ValidityState.typeMismatch' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`typeMismatch`

15

12

4

10

12.1

5

≤37

18

4

12.1

5

1.0

See also
--------

-   [Constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation)
-   [Forms: Data form validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)
-   [Regular Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/typeMismatch" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/typeMismatch</a>
