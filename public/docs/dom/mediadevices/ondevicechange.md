# MediaDevices.ondevicechange

The `MediaDevices.ondevicechange` property is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) which specifies a function to be called when the `devicechange` event occurs on a [`MediaDevices`](../mediadevices) instance. This happens whenever the set of media devices available to the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) and, by extension, to the web site or app has changed. You can at any time use [`enumerateDevices()`](enumeratedevices) to get the updated list of available devices.

## Syntax

    MediaDevices.ondevicechange = eventHandler;

### Value

A function you provide which accepts as input a [`Event`](../event) object describing the `devicechange` event that occurred. There is no information about the change included in the event object; to get the updated list of devices, you'll have to use [`enumerateDevices()`](enumeratedevices).

## Example

In this example, we create a function called `updateDeviceList()`, which is called once when [`MediaDevices.getUserMedia()`](getusermedia) successfully obtains a stream, and then is called any time the device list changes. It displays in the browser window two lists: one of audio devices and one of video devices, with both the device's label (name) and whether it's an input or an output device. Because the example provides a handler for the `devicechange` event, the list is refreshed any time a media device is attached to or removed from the device running the sample.

We set up global variables that contain references to the [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) elements that are used to list the audio and video devices:

    let audioList = document.getElementById("audioList");
    let videoList = document.getElementById("videoList");

#### Getting and drawing the device list

Now let's take a look at `updateDeviceList()` itself. This method is called any time we want to fetch the current list of media devices and then update the displayed lists of audio and video devices using that information.

    function updateDeviceList() {
      navigator.mediaDevices.enumerateDevices()
      .then(function(devices) {
        audioList.innerHTML = "";
        videoList.innerHTML = "";

        devices.forEach(function(device) {
          let elem = document.createElement("li");
          let [kind, type, direction] = device.kind.match(/(\w+)(input|output)/i);

          elem.innerHTML = "<strong>" + device.label + "</strong> (" + direction + ")";
          if (type === "audio") {
            audioList.appendChild(elem);
          } else if (type === "video") {
            videoList.appendChild(elem);
          }
        });
      });
    }

`updateDeviceList()` consists entirely of a call to the function [`enumerateDevices()`](enumeratedevices) on the [`MediaDevices`](../mediadevices) object referenced in the [`navigator.mediaDevices`](../navigator/mediadevices) property, as well as the code that's run when the [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by `enumerateDevices()` is fulfilled. The fulfillment handler is called when the device list is ready. The list is passed into the fulfillment handler as an array of [`MediaDeviceInfo`](../mediadeviceinfo) objects, each describing one media input or output device.

A [`forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) loop is used to scan through all the devices. For each device, we create a new [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li) object to be used to display it to the user.

The line `let [kind, type, direction] = device.kind.match(/(\w+)(input|output)/i);` deserves special notice. This uses [destructuring assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment) (a new feature of [ECMAScript 6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/New_in_JavaScript/ECMAScript_6_support_in_Mozilla)) to assign the values of the first three items in the array returned by [`String.match()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/match) to the variables `kind`, `type`, and `direction`. We do this because the value of [`MediaDeviceInfo.kind`](../mediadeviceinfo/kind) is a single string that includes both the media type and the direction the media flows, such as "audioinput" or "videooutput". This line, then, pulls out the type ("audio" or "video") and direction ("input" or "output") so they can be used to construct the string displayed in the list.

Once the string is assembled, containing the device's name in bold and the direction in parentheses, it's appended to the appropriate list by calling [`appendChild()`](../node/appendchild) on either `audioList` or `videoList`, as appropriate based on the device type.

#### Handling device list changes

We call `updateDeviceList()` in two places. The first is in the [`getUserMedia()`](getusermedia) promise's fulfillment handler, to initially fill out the list when the stream is opened. The second is in the event handler for `devicechange`:

    navigator.mediaDevices.ondevicechange = function(event) {
      updateDeviceList();
    }

With this code in place, each time the user plugs in a camera, microphone, or other media device, or turns one on or off, we call `updateDeviceList()` to redraw the list of connected devices.

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediadevices-ondevicechange">Media Capture and Streams<br />
<span class="small">The definition of 'ondevicechange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`ondevicechange`

57

12

52

No

34

11

No

No

Yes

34

11

No

## See also

- The `devicechange` event and its type, [`Event`](../event).
- [`MediaDevices.enumerateDevices()`](enumeratedevices)
- [`MediaDeviceInfo`](../mediadeviceinfo)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/ondevicechange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/ondevicechange</a>
