# mssitemodejumplistitemremoved event

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `mssitemodejumplistitemremoved` event occurs when `msSiteModeShowJumpList` is called and an item has been removed from a _Jump List_ by the user.

This proprietary method is specific to Internet Explorer and Microsoft Edge.

## Syntax

<table><tbody><tr class="odd"><td>Event Property</td><td>object.oncandidatewindowhide = handler;</td></tr><tr class="even"><td>addEventListener Method</td><td>object.addEventListener("mssitemodejumplistitemremoved", handler, useCapture)</td></tr></tbody></table>

## General info

Synchronous  
No

Bubbles  
No

Cancelable  
No

### Note

This event is raised once for every item that has been removed since the last time `msSiteModeShowJumpList `was called. This event is not triggered if `msSiteModeClearJumpList `has been called.

### Parameters

**pEvtObj** \[in\]

Type: _IHTMLEventObj_

Pointer to an IHTMLEventObj interface for the current event.

## See also

- [Microsoft API extensions](microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/mssitemodejumplistitemremoved" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/mssitemodejumplistitemremoved</a>
