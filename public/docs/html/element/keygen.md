&lt;keygen&gt;
==============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The HTML `<keygen>` element exists to facilitate generation of key material, and submission of the public key as part of an [HTML form](https://developer.mozilla.org/en-US/docs/Learn/Forms). This mechanism is designed for use with Web-based certificate management systems. It is expected that the `<keygen>` element will be used in an HTML form along with other information needed to construct a certificate request, and that the result of the process will be a signed certificate.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, interactive content, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_listed">listed</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_labelable">labelable</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_submittable">submittable</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_resettable">resettable</a> <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form-associated_content">form-associated element</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td>None, it is an <a href="https://developer.mozilla.org/en-US/docs/Glossary/Empty_element">empty element</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>Must have a start tag and must not have an end tag.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Permitted ARIA roles</td><td>None</td></tr><tr class="even"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLKeygenElement"><code>HTMLKeygenElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

`autofocus`  
This Boolean attribute lets you specify that the control should have input focus when the page loads, unless the user overrides it, for example by typing in a different control. Only one form element in a document can have the `autofocus` attribute, which is a Boolean.

`challenge`  
A challenge string that is submitted along with the public key. Defaults to an empty string if not specified.

`disabled`  
This Boolean attribute indicates that the form control is not available for interaction.

`form`  
The form element that this element is associated with (its *form owner*). The value of the attribute must be an `id` of a [`<form>`](form) element in the same document. If this attribute is not specified, this element must be a descendant of a [`<form>`](form) element. This attribute enables you to place `<keygen> `elements anywhere within a document, not just as descendants of their form elements.

`keytype`  
The type of key generated. The default value is `RSA`.

`name`  
The name of the control, which is submitted with the form data.

The element is written as follows:

    <keygen name="name" challenge="challenge string" keytype="type"
            keyparams="pqg-params">

The `keytype` parameter is used to specify what type of key is to be generated. Valid values are "`RSA`", which is the default, "`DSA`" and "`EC`". The `name` and `challenge` attributes are required in all cases. The `keytype` attribute is optional for RSA key generation and required for DSA and EC key generation. The `keyparams` attribute is required for DSA and EC key generation and ignored for RSA key generation. `PQG` is a synonym for `keyparams`. That is, you may specify `keyparams="pqg-params"` or `pqg="pqg-params"`.

For RSA keys, the `keyparams` parameter is not used (ignored if present). The user may be given a choice of RSA key strengths. Currently, the user is given a choice between "high" strength (2048 bits) and "medium" strength (1024 bits).

For DSA keys, the `keyparams` parameter specifies the DSA PQG parameters which are to be used in the keygen process. The value of the `pqg` parameter is the BASE64 encoded, DER encoded Dss-Parms as specified in IETF <a href="ftp://ftp.rfc-editor.org/in-notes/rfc3279.txt" class="link-ftp">RFC 3279</a>. The user may be given a choice of DSA key sizes, allowing the user to choose one of the sizes defined in the DSA standard.

For EC keys, the `keyparams` parameter specifies the name of the elliptic curve on which the key will be generated. It is normally a string from the table in [nsKeygenHandler.cpp](http://mxr.mozilla.org/mozilla-central/source/security/manager/ssl/src/nsKeygenHandler.cpp?mark=179-185,187-206,208-227,229-256#177). (Note that only a subset of the curves named there may actually be supported in any particular browser.) If the `keyparams` parameter string is not a recognized curve name string, then a curve is chosen according to the user's chosen key strength (low, medium, high), using the curve named "`secp384r1`" for high, and the curve named "`secp256r1`" for medium keys. (Note: choice of the number of key strengths, default values for each strength, and the UI by which the user is offered a choice, are outside of the scope of this specification.)

The `<keygen>` element is only valid within an HTML form. It will cause some sort of selection to be presented to the user for selecting key size. The UI for the selection may be a menu, radio buttons, or possibly something else. The browser presents several possible key strengths. Currently, two strengths are offered, high and medium. If the user's browser is configured to support cryptographic hardware (e.g. "smart cards") the user may also be given a choice of where to generate the key, i.e., in a smart card or in software and stored on disk.

When the submit button is pressed, a key pair of the selected size is generated. The private key is encrypted and stored in the local key database.

    PublicKeyAndChallenge ::= SEQUENCE {
        spki SubjectPublicKeyInfo,
        challenge IA5STRING
    }
    SignedPublicKeyAndChallenge ::= SEQUENCE {
        publicKeyAndChallenge PublicKeyAndChallenge,
        signatureAlgorithm AlgorithmIdentifier,
        signature BIT STRING
    }

The public key and challenge string are DER encoded as `PublicKeyAndChallenge`, and then digitally signed with the private key to produce a `SignedPublicKeyAndChallenge`. The `SignedPublicKeyAndChallenge` is [Base64](https://developer.mozilla.org/en-US/docs/Glossary/Base64) encoded, and the ASCII data is finally submitted to the server as the value of a form name/value pair, where the name is name as specified by the `name` attribute of the `keygen` element. If no challenge string is provided, then it will be encoded as an `IA5STRING` of length zero.

Here is an example form submission as it would be delivered to a CGI program by the HTTP server:

       commonname=John+Doe&email=doe@foo.com&org=Foobar+Computing+Corp.&
       orgunit=Bureau+of+Bureaucracy&locality=Anytown&state=California&country=US&
       key=MIHFMHEwXDANBgkqhkiG9w0BAQEFAANLADBIAkEAnX0TILJrOMUue%2BPtwBRE6XfV%0AWtKQbsshxk5ZhcUwcwyvcnIq9b82QhJdoACdD34rqfCAIND46fXKQUnb0mvKzQID%0AAQABFhFNb3ppbGxhSXNNeUZyaWVuZDANBgkqhkiG9w0BAQQFAANBAAKv2Eex2n%2FS%0Ar%2F7iJNroWlSzSMtTiQTEB%2BADWHGj9u1xrUrOilq%2Fo2cuQxIfZcNZkYAkWP4DubqW%0Ai0%2F%2FrgBvmco%3D

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#the-keygen-element">HTML 5.1<br />
<span class="small">The definition of 'the <code>&lt;keygen&gt;</code> element' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`keygen`

Yes-57

≤18-79

1-69

No

3

1.2

Yes-57

Yes-57

4

?

No

Yes-7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/keygen" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/keygen</a>
