msSetMediaProtectionManager
===========================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `msSetMediaProtectionManager` method specifies the media protection manager for a given media pipeline.

This proprietary method is specific to Internet Explorer and Microsoft Edge.

Syntax
------

    HTMLMediaElement.msSetMediaProtectionManager(mediaProtectionManager);

### Parameters

The [Windows.Media.Protection](https://docs.microsoft.com/en-us/uwp/api/windows.media.protection) namespace provides classes to manage Digital Rights Management (DRM) media contents. The `MediaProtectionManager` class can be passed as an input to a media playback API or the `mediaProtectionManager` property inside the tag's video or audio.

The optional parameter of the `msSetMediaProtectionManager` property is `mediaProtectionManager` and can be any type.

### Return value

This method does not return a value.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MsSetMediaProtectionManager" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MsSetMediaProtectionManager</a>
