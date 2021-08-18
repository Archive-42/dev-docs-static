RTCRtpSender.setParameters()
============================

The `setParameters()` method of the [`RTCRtpSender`](../rtcrtpsender) interface applies changes the configuration of sender's [`track`](track), which is the [`MediaStreamTrack`](../mediastreamtrack) for which the `RTCRtpSender` is responsible.

In other words, `setParameters()` updates the configuration of the [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) transmission as well as the encoding configuration for a specific outgoing media track on the [WebRTC](../webrtc_api) connection.

Syntax
------

    var promise = rtcRtpSender.setParameters(parameters)

### Parameters

`parameters`  
A parameters object previously obtained by calling the same sender's [`getParameters()`](getparameters) method, with the desired changes to the sender's configuration parameters. These parameters include potential codecs that could be use for encoding the sender's [`track`](track). The available parameters are:

[`encodings`](../rtcrtpsendparameters/encodings)  
An array of [`RTCRtpEncodingParameters`](../rtcrtpencodingparameters) objects, each specifying the parameters for a single codec that could be used to encode the track's media.

<span class="page-not-created">`transactionId`</span>  
A string containing a unique ID for the last set of parameters applied; this value is used to ensure that [`setParameters()`](setparameters) can only be called to alter changes made by a specific previous call to [`getParameters()`](getparameters). Once this parameter is initially set, it cannot be changed.

### Obsolete properties

 <span class="page-not-created">`degradationPreference`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Specifies the preferred way the WebRTC layer should handle optimizing bandwidth against quality in constrained-bandwidth situations; the value comes from the <span class="page-not-created">`RTCDegradationPreference`</span> enumerated string type, and the default is `balanced`.

 <span class="page-not-created">`priority`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A string from the <span class="page-not-created">`RTCPriorityType`</span> enumerated type which indicates the encoding's priority. The default value is `low`.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the [`RTCRtpSender.track`](track) property is updated with the given parameters.

### Exceptions

If an error occurs, the returned promise is rejected with the appropriate exception from the list below.

`InvalidModificationError`  
One of the following problems was detected:

-   The number of encodings specified in the `parameters` object's [`encodings`](../rtcrtpsendparameters/encodings) property does not match the number of encodings currently listed for the `RTCRtpSender`. You cannot change the number of encoding options once the sender has been created.
-   The order of the specified `encodings` has changed from the current list's order.
-   An attempt has been made to alter a property that cannot be changed after the sender is first created.

`InvalidStateError`  
The transceiver of which the `RTCRtpSender` is a part is not running, or has no parameters to set.

`OperationError`  
Any error condition which occurs that isn't covered by one of the other error codes results in an `OperationError`.

`RangeError`  
The value specified for <span class="page-not-created">`scaleResolutionDownBy`</span> is less than 1.0, which would result in scaling up rather than down, which is not allowed; or one or more of the specified encodings' <span class="page-not-created">`maxFramerate`</span> values is less than 0.0.

In addition, if a WebRTC error occurs while configuring or accessing the media, an [`RTCError`](../rtcerror) is thrown with its [`errorDetail`](../rtcerror/errordetail) set to `hardware-encoder-error`.

Description
-----------

It's important to keep in mind that you can't create an [`RTCRtpSendParameters`](../rtcrtpsendparameters) object yourself and expect it to work. Instead, you *must* first call [`getParameters()`](getparameters), modify the received parameters object, then pass that object into `setParameters()`. WebRTC uses the parameters object's `transactionId` property to ensure that when you set parameters, your changes are based on the most recent parameters rather than an out of date configuration.

Examples
--------

One use case for `setParameters()` is to try to reduce network bandwidth use in constrained environments by altering the resolution and/or bit rate of the media being transmitted by the [`RTCRtpSender`](../rtcrtpsender).

Currently, some browsers have limitations on their implementations that may cause issues. For that reason, two examples are given here. The first shows how to use `setParameters()` when all browsers fully support the parameters being used, while the second example demonstrates workarounds to help solve limitations in browsers with incomplete support for the [`maxBitrate`](../rtcrtpencodingparameters/maxbitrate) and [`scaleResolutionDownBy`](../rtcrtpencodingparameters/scaleresolutiondownby) parameters.

### By the specification

Once all browsers implement the spec fully, this implementation of `setVideoParams()` will do the job. This demonstrates how everything *should* work. You should probably use the second example, below, for now. But this is a clearer demonstration of the basic concept of first fetching the parameters, then altering them, then setting them.

    async function setVideoParams(sender, height, bitrate) {
      const scaleRatio = sender.track.getSettings().height/height;
      const params = sender.getParameters();

      params.encodings[0].scaleResolutionDownBy = Math.max(ratio, 1);
      params.encodings[0].maxBitrate = bitrate;
      await sender.setParameters(params);
    }

In calling this function, you specify a sender, as w.ell as the height you wish to scale the sender's video to, as well as a maximum bitrate to permit the sender to transmit. A scaling factor for the size of the video, `scaleRatio`, is computed. Then the sender's current parameters are fetched using [`getParameters()`](getparameters).

The parameters are then altered by changing the first [`encodings`](../rtcrtpsendparameters/encodings) object's [`scaleResolutionDownBy`](../rtcrtpencodingparameters/scaleresolutiondownby) and [`maxBitrate`](../rtcrtpencodingparameters/maxbitrate) to the calculated scaling factor and the specified maximum `bitrate`.

The changed parameters are then saved by calling the sender's `setParameters()` method.

### Currently compatible implementation

As mentioned above, the previous example shows how things are meant to work. Unfortunately, there are implementation issues preventing this in many browsers right now. For that reason, if you want to be compatible with iPhone and other devices running Safari, and with Firefox, use code more like this:

    async function setVideoParams(sender, height, bitrate) {
      const scaleRatio = sender.track.getSettings().height/height;
      const params = sender.getParameters();

      // If encodings is null, create it

      if (!params.encodings) {
        params.encodings = [{ }];
      }

      params.encodings[0].scaleResolutionDownBy = Math.max(ratio, 1);
      params.encodings[0].maxBitrate = bitrate;
      await sender.setParameters(params);

      // If the newly changed value of scaleResolutionDownBy is 1,
      // use applyConstraints() to be sure the height is constrained,
      // since scaleResolutionDownBy may not be implemented

      if (sender.getParameters().encodings[0].scaleResolutionDownBy == 1) {
        await sender.track.applyConstraints({ height });
      }
    }

The differences here:

-   If `encodings` is `null`, we create it, in order to ensure that we can then set the parameters successfully without crashing.
-   If, after setting the parameters, the value of `scaleResolutionDownBy` is still 1, we call the sender's track's [`applyConstraints()`](../mediastreamtrack/applyconstraints) method to constrain the track's height to `height`. This compensates for an unimplemented `scaleResolutionDownBy` (as is the case in Safari as of this writing).

This code will cleanly fall back and work the normal way if the browser fully implements the used features.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpsender-setparameters">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpSender.setParameters()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`setParameters`

68

≤79

64

Changes to parameters that should update live now do so starting in Firefox 64.

46

No

55

12.1

68

68

64

Changes to parameters that should update live now do so starting in Firefox 64.

46

48

12.2

10.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   [Codecs used by WebRTC](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/WebRTC_codecs)
-   [Web media technologies](https://developer.mozilla.org/en-US/docs/Web/Media)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/setParameters" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/setParameters</a>
