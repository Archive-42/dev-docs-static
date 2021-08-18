# Navigator.buildID

Returns the build identifier of the browser. In modern browsers this property now returns a fixed timestamp as a privacy measure, e.g. `20181001000000` in Firefox 64 onwards.

## Syntax

    buildID = navigator.buildID;

### Value

A string representing the build identifier of the application. The build ID is in the form `YYYYMMDDHHMMSS`.

## Example

    console.log(window.navigator.buildID);

## Specifications

Not part of any public standard.

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

`buildID`

No

No

64

Returns a fixed timestamp as a privacy measure - `20181001000000`.

2

No

?

?

No

No

64

Returns a fixed timestamp as a privacy measure - `20181001000000`.

Yes

?

?

No

## See also

- [navigator.buildID now returns a fixed timestamp](https://github.com/mdn/kuma/issues/7647)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/buildID" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/buildID</a>
