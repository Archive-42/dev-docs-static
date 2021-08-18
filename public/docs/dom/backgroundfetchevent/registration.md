# BackgroundFetchEvent.registration

The `registration` read-only property of the [`BackgroundFetchEvent`](../backgroundfetchevent) interface returns a [`BackgroundFetchRegistration`](../backgroundfetchregistration) object.

## Syntax

    let registration = BackgroundFetchEvent.registration;

### Value

A [`BackgroundFetchRegistration`](../backgroundfetchregistration).

## Examples

In this example, if the user clicks on the user interface displaying the download progress, this fires the `onbackgroundfetchclick` event. The current [`BackgroundFetchRegistration`](../backgroundfetchregistration) is returned by calling `event.registration`.

    addEventListener('backgroundfetchclick', (event) => {
      console.log(event.registration);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#dom-backgroundfetcheventinit-registration">Background Fetch<br />
<span class="small">The definition of 'BackgroundFetchEvent.registration' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`registration`

74

79

No

No

62

No

No

74

No

53

No

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchEvent/registration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchEvent/registration</a>
