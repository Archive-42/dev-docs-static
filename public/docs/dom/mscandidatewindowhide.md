# MSCandidateWindowHide

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

`MSCandidateWindowHide` fires after the Input Method Editor (IME) candidate window closes and is fully hidden.

This proprietary method is specific to Internet Explorer.

## General info

Synchronous  
No

Bubbles  
No

Cancelable  
No

### Note

Windows 8.1 and Windows 7 IMEs for certain languages on Internet Explorer for the desktop might not support this event. On Internet Explorer in the new Windows UI, this event is supported in Windows 8.1 IMEs of all languages.

## Syntax

<table><tbody><tr class="odd"><td>Event Property</td><td>object.oncandidatewindowhide = handler;</td></tr><tr class="even"><td>addEventListener Method</td><td>object.addEventListener("MSCandidateWindowHide", handler, useCapture)</td></tr></tbody></table>

nbsp;

### Parameters

**pEvtObj** \[in\]

Type: _IHTMLEventObj_

Pointer to an IHTMLEventObj interface for the current event.

The handler of this event will see that the isCandidateWindowVisible method returns false, and no ClientRect object is returned from getCandidateWindowClientRect.

Web applications need only register for this event once per element (the handler will remain valid for the lifetime of the element).

## See also

- [Microsoft API extensions](microsoft_extensions)
- [IME handling guide for Gecko](https://developer.mozilla.org/en-US/docs/Mozilla/IME_handling_guide)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MSCandidateWindowHide" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MSCandidateWindowHide</a>
