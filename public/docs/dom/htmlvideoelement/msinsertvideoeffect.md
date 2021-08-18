HTMLVideoElement.msInsertVideoEffect()
======================================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `HTMLMediaElement.msInsertVideoEffect()` method inserts the specified video effect into the media pipeline.

This proprietary method is specific to Internet Explorer and Microsoft Edge.

Syntax
------

    str = HTMLMediaElement.msInsertVideoEffect(activatableClassId: DOMString, effectRequired: boolean, config);

### Parameters

activatableClassId  
A [`DOMString`](../domstring) defining the video effects class.

effectRequired  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)which if set to *true* requires a video effect to be defined.

config<span class="badge inline optional">Optional</span>   
An optional [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) to help with defining any additional configuration needed.

### Return value

This method does not return a value.

Example
-------

    var oVideo1 = document.getElementById("video1");
    oVideo1.msInsertVideoEffect("Windows.Media.VideoEffects.VideoStabilization", true, null);

See also
--------

-   [`HTMLVideoElement`](../htmlvideoelement)
-   [Microsoft API extensions](../microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/msInsertVideoEffect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/msInsertVideoEffect</a>
