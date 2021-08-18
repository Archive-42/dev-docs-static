msPlayToSource
==============

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

`msPlayToSource` is a read-only property which gets the source associated with the media element for use by the [`PlayToManager`](https://docs.microsoft.com/en-us/uwp/api/windows.media.playto.playtomanager).

This proprietary property is specific to Internet Explorer and Microsoft Edge.

Syntax
------

    ptr = object.msPlayToSource;

Value
-----

*PlayTo* is a means through which an app can connect local playback/display for audio, video, and img elements to a remote device. For more information, see the [Windows.Media.PlayTo](https://docs.microsoft.com/en-us/uwp/api/windows.media.playto) APIs.

`msPlayToSource` is used in the `sourceRequested` handler -- get the `PlayToSource` object from an audio, video, or img element using the `msPlayToSource` property and pass it to `e.setSource`, then set the `PlayToSource.next` property to the `msPlayToSource` of another element for continual playing.

The property value for `msPlayToSource` is the source associated with the media element.

Example
-------

    <video id="videoplayer" src="http://www.contoso.com/clip.mp4" controls autoplay />
    <script type="text/javascript">

      // Step 1: Obtain PlayToManager object for app’s current view.
        var ptm = Windows.Media.PlayTo.PlayToManager.getForCurrentView();

      // Step 2: Register for the sourcerequested event (user swipes Devices charm).
        ptm.addEventListener("sourcerequested", function(e) {

      // Step 3: Specify the media to be streamed (to filter devices).
            e.sourceRequest.setSource(document.getElementById("videoplayer").msPlayToSource);

      // The media will then be streamed to the device chosen by the user in the UI.

        });

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MsPlayToSource" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MsPlayToSource</a>
