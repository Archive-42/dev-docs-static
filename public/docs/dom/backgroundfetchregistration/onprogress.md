# BackgroundFetchRegistration.onprogress

The `onprogress` EventHandler of the [`BackgroundFetchRegistration`](../backgroundfetchregistration) interface is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes background fetch events.

The event fires when any of the following properties change:

- `uploaded`
- `downloaded`
- `result`
- `failureReason`

## Syntax

    BackgroundFetchRegistration.onprogress = function;
    BackgroundRegistration.addEventListener('progress', function);

Where `function` is the JavaScript function to execute.

## Example

The following example demonstrates how to log the progress of a download. The code first checks that a `downloadTotal` was provided when the background fetch was registered. This is then used to calculate the percentage, based on the `downloaded` property.

    bgFetch.addEventListener('progress', () => {
      if (!bgFetch.downloadTotal) return;
      const percent = Math.round(bgFetch.downloaded / bgFetch.downloadTotal * 100);
      console.log(`Download progress: ${percent}%`);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#dom-backgroundfetchregistration-onprogress">Background Fetch<br />
<span class="small">The definition of 'BackgroundFetchRegistration.onprogress' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onprogress`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRegistration/onprogress" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRegistration/onprogress</a>
