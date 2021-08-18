# msPlayToPreferredSourceUri

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

`msPlayToPreferredSourceUri` is a read/write property which gets or sets the path to the preferred media source. This enables the _PlayTo_ target device to stream the media content, which can be DRM protected, from a different location, such as a cloud media server.

This proprietary property is specific to Internet Explorer and Microsoft Edge.

## Syntax

    ptr = object.msPlayToPreferredSourceUri;

## Value

`msPlayToPreferredSourceUri` enables a _PlayTo_ reference (a URI or URL) for streaming content on the _PlayTo_ target device from a different location, such as a cloud media server. This enables web pages and Microsoft Store apps to play Digital Rights Management (DRM) protected content. The app specifies a preferred Uniform Resource Identifier (URI). This URI can point to a cloud based media server allowing streaming directly from the cloud, which can be DRM protected, instead of streaming content from the Windows machine which must be unprotected content.

A forward slash ("/") is appended to the URI string when it is sent over the network to a _PlayTo_ device. This is done to conform to URI standards.

## Example

      <video src="http://www.contoso.com/videos/video.mp4"
           msPlayToPreferredSourceUri="http://www.contoso.com/catalogid=1234" />

      var video = document.createElement('video');
      document.body.appendChild(video);

      video.src = "http://www.contoso.com/videos/video.mp4";
      video.msPlayToPreferredSourceUri = "http://www.contoso.com/catalogid=1234";

## See also

- [Microsoft PlayReady](https://docs.microsoft.com/en-us/playready/) content access and protection technology is a set of technologies that can be used to distribute audio/video content more securely over a network, and help prevent the unauthorized use of this content.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MsPlayToPreferredSourceUri" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MsPlayToPreferredSourceUri</a>
