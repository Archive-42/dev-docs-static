# HTMLKeygenElement

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Note:** This page describes the Keygen Element interface as specified, not as currently implemented by Gecko. See [bug 101019](https://bugzilla.mozilla.org/show_bug.cgi?id=101019) for details and status.

The [`<keygen>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/keygen) elements expose the `HTMLKeygenElement` interface, which provides special properties and methods (beyond the regular [`element`](element) object interface they also have available to them by inheritance) for manipulating the layout and presentation of `keygen` elements.

## Properties

autofocus  
Is a `Boolean` that reflects the [`autofocus`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/keygen#attr-autofocus) HTML attribute, indicating that the form control should have input focus when the page loads.

challenge  
Is a `DOMString` that reflects the [`challenge`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/keygen#attr-challenge) HTML attribute, containing a challenge string that is packaged with the submitted key.

form <span class="badge inline readonly">Read only </span>  
Is a `HTMLFormElement` that indicates the control's form owner, reflecting the [`form`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/keygen#attr-form) HTML attribute if it is defined.

keytype  
Is a `DOMString` that reflects the [`keytype`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/keygen#attr-keytype) HTML attribute, containing the type of key used.

labels <span class="badge inline readonly">Read only </span> <span class="notecard inline warning">Unimplemented (see [bug 556743](https://bugzilla.mozilla.org/show_bug.cgi?id=556743))</span>  
Is a `NodeList` that represents a list of label elements associated with this keygen element.

name  
Is a `DOMString` that reflects the [`name`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/keygen#attr-name) HTML attribute, containing the name for the control that is submitted with form data.

type <span class="badge inline readonly">Read only </span>  
Is a `DOMString` that must be the value `keygen`.

validationMessage <span class="badge inline readonly">Read only </span>  
Is a `DOMString` representing a localized message that describes the validation constraints that the control does not satisfy (if any). This is the empty string if the control is not a candidate for constraint validation (`willValidate` is false), or it satisfies its constraints.

validity <span class="badge inline readonly">Read only </span>  
Is a `ValidityState` representing the validity states that this element is in.

willValidate  
Is a `Boolean` that is always false because `keygen` objects are never candidates for constraint validation.

## Methods

<table><thead><tr class="header"><th>Name &amp; Arguments</th><th>Return</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>checkValidity()</code></td><td><code>Boolean</code></td><td>Always returns true because <code>keygen</code> objects are never candidates for constraint validation.</td></tr><tr class="even"><td><code>setCustomValidity(in DOMString error)</code></td><td><code>void</code></td><td>Sets a custom validity message for the element. If this message is not the empty string, then the element is suffering from a custom validity error, and does not validate.</td></tr></tbody></table>

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

`HTMLKeygenElement`

10-57

See [Chrome Platform Status](https://www.chromestatus.com/features/5716060992962560).

?

1-69

No

≤12.1-44

5.1-13.1

≤37-57

See [Chrome Platform Status](https://www.chromestatus.com/features/5716060992962560).

18-57

See [Chrome Platform Status](https://www.chromestatus.com/features/5716060992962560).

4-79

Never fully implemented. See [bug 1315460](https://bugzil.la/1315460).

≤12.1-43

5-13.4

1.0-7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLKeygenElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLKeygenElement</a>
