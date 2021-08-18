# MediaDevices.getSupportedConstraints()

The ` getSupportedConstraints``() ` method of the [`MediaDevices`](../mediadevices) interface returns an object based on the [`MediaTrackSupportedConstraints`](../mediatracksupportedconstraints) dictionary, whose member fields each specify one of the constrainable properties the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) understands.

## Syntax

    var supportedConstraints = navigator.mediaDevices.getSupportedConstraints();

### Parameters

None.

### Return value

A new object based on the [`MediaTrackSupportedConstraints`](../mediatracksupportedconstraints) dictionary listing the constraints supported by the user agent. Because only constraints supported by the user agent are included in the list, each of these Boolean properties has the value `true`.

## Example

This example outputs a list of the constraints supported by your browser.

    let constraintList = document.getElementById("constraintList");
    let supportedConstraints = navigator.mediaDevices.getSupportedConstraints();

    for (let constraint in supportedConstraints) {
      if (supportedConstraints.hasOwnProperty(constraint)) {
        let elem = document.createElement("li");

        elem.innerHTML = "<code>" + constraint + "</code>";
        constraintList.appendChild(elem);
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediadevices-getsupportedconstraints">Media Capture and Streams<br />
<span class="small">The definition of 'getSupportedConstraints()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getSupportedConstraints`

53

12

44

No

40

11

53

52

50

41

11

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getSupportedConstraints" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getSupportedConstraints</a>
