# Presentation

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `Presentation` can be defined as two possible user agents in the context: _Controlling user agent_ and _Receiving user agent_.

In controlling browsing context, the `Presentation` interface provides a mechanism to override the browser default behavior of launching presentation to external screen. In receiving browsing context, `Presentation` interface provides the access to the available presentation connections.

## Properties

[`Presentation.defaultRequest`](presentation/defaultrequest)  
In a [controlling user agent](https://www.w3.org/TR/presentation-api/#dfn-controlling-user-agent), the `defaultRequest` attribute _MUST_ return the [default presentation request](https://www.w3.org/TR/presentation-api/#dfn-default-presentation-request) if any, `null` otherwise. In a [receiving browsing context](https://www.w3.org/TR/presentation-api/#dfn-receiving-browsing-context), it _MUST_ return `null`.

[`Presentation.receiver`](presentation/receiver)  
In a [receiving user agent](https://www.w3.org/TR/presentation-api/#dfn-receiving-user-agent), the `receiver` attribute _MUST_ return the [`PresentationReceiver`](presentationreceiver) instance associated with the [receiving browsing context](https://www.w3.org/TR/presentation-api/#dfn-receiving-browsing-context) and created by the [receiving user agent](https://www.w3.org/TR/presentation-api/#dfn-receiving-user-agent) when the [receiving browsing context](https://www.w3.org/TR/presentation-api/#dfn-receiving-browsing-context) is created.

## Methods

None.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/presentation-api/#interface-presentation">Presentation API<br />
<span class="small">The definition of 'Presentation interface' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Presentation`

48

≤79

51-88

No

Yes

No

No

48

51-79

Yes

No

5.0

`defaultRequest`

48

≤79

51-88

No

Yes

No

No

48

51-79

Yes

No

5.0

`receiver`

48

≤79

51-88

No

Yes

No

No

48

51-79

Yes

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Presentation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Presentation</a>
