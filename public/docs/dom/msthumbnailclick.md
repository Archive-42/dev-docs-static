# msthumbnailclick event

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `msthumbnailclick` event occurs when a user clicks a button or thumbnail icon in the taskbar.

This proprietary method is specific to Internet Explorer and Microsoft Edge.

## Syntax

<table><tbody><tr class="odd"><td>Event Property</td><td>object.onmsthumbnailclick = handler;</td></tr><tr class="even"><td>addEventListener Method</td><td>object.addEventListener("msthumbnailclick", handler, useCapture)</td></tr></tbody></table>

## General info

Synchronous  
No

Bubbles  
No

Cancelable  
No

### Note

The onmsthumbnailclick event is available only to documents that are launched from a pinned site shortcut.

### Parameters

**pEvtObj** \[in\]

Type: _IHTMLEventObj_

Pointer to an IHTMLEventObj interface for the current event.

## Example

    function thumbnailClickHandler(evt)
    {
        alert ("Clicked button: " + evt.buttonID);
    }
    document.addEventListener('msthumbnailclick', thumbnailClickHandler);

## Example 2

    // Adds an overlay icon on your app pinned to the taskbar
    window.external.msSiteModeSetIconOverlay(iconUri, toolTip);

    // removes an overlay icon
    window.external.msSiteModeClearIconOverlay();

    // pinned icons on your taskbar can be instructed to trigger specific events on your site from the taskbar
    // add an event
    handlerdocument.addEventListener('msthumbnailclick', onButtonClicked, false);

    // add the buttons
    var btnPlay = window.external.msSiteModeAddThumbBarButton(iconUri, toolTip);

    // refresh the taskbar
    window.external.msSiteModeShowThumbBar();

    // call a javascript function when the button is pressed
    function onButtonClicked(e) {
       switch (e.buttonID) {
         case btnPlay: play();
         break;}
     }

## See also

- [Microsoft API extensions](microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/msthumbnailclick" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/msthumbnailclick</a>
