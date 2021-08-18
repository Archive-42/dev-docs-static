# MSGraphicsTrust

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `msGraphicsTrust()` constructor returns an object that provides properties for info on protected video playback.

This proprietary method is specific to Internet Explorer and Microsoft Edge.

## Syntax

    var trustObject = media.msGraphicsTrustStatus;

### Parameters

constrictionActive  
A read-only property which returns _true_ when protected media is forced to play in a lower resolution.

status  
A read-only property which returns an enum with the driver status when playing protected content.

### Inheritance hierarchy

The MSGraphicsTrust does not inherit from any class or interface.

## Example

    var trustObject = media.msGraphicsTrustStatus;

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MSGraphicsTrust" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MSGraphicsTrust</a>
