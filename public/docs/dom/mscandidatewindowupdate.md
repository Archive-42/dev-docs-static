MSCandidateWindowUpdate
=======================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

`MSCandidateWindowUpdate` fires after the Input Method Editor (IME) candidate window has been identified as needing to change size, but before any visual updates have rendered.

This proprietary method is specific to Internet Explorer.

General info
------------

Synchronous  
No

Bubbles  
No

Cancelable  
No

### Note

Windows 8.1 and Windows 7 IMEs for certain languages on Internet Explorer for the desktop might not support this event. On Internet Explorer in the new Windows UI, this event is supported in Windows 8.1 IMEs of all languages.

Syntax
------

<table><tbody><tr class="odd"><td>Event Property</td><td>object.oncandidatewindowupdate = handler;</td></tr><tr class="even"><td>addEventListener Method</td><td>object.addEventListener("MSCandidateWindowUpdate", handler, useCapture)</td></tr></tbody></table>

### Parameters

**pEvtObj** \[in\]

Type: *IHTMLEventObj*

Pointer to an `IHTMLEventObj `interface for the current event.

TAn IME candidate window may be identified as needing to change size for any of the following reasons:

-   As a result of displaying new / changed alternatives or predictions

Web applications need only register for this event once per element (the handler will remain valid for the lifetime of the element).

See also
--------

-   [Microsoft API extensions](microsoft_extensions)
-   [IME handling guide for Gecko](https://developer.mozilla.org/en-US/docs/Mozilla/IME_handling_guide)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MSCandidateWindowUpdate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MSCandidateWindowUpdate</a>
