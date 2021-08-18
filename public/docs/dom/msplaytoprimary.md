# msPlayToPrimary

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

`msPlayToPrimary` is a read/write property which gets or sets the primary DLNA _PlayTo_ device.

This proprietary property is specific to Internet Explorer and Microsoft Edge.

## Syntax

    ptr = object.msPlayToPrimary;

## Value

Boolean value set to _true_ indicates that the device is the primary DLNA _PlayTo_ device, otherwise false.

## Example

         // Microsoft extensions
         interface HTMLImageElement : HTMLElement
         {
                      attribute boolean msPlayToDisabled;
                      attribute boolean msPlayToPrimary;
                      attribute DOMString msPlayToPreferredSourceUri;
         };

## See also

- [HTMLMediaElement](htmlmediaelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MsPlayToPrimary" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MsPlayToPrimary</a>
