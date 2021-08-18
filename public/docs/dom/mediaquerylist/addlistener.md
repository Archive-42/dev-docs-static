# MediaQueryList.addListener()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The deprecated `addListener()` method of the [`MediaQueryList`](../mediaquerylist) interface adds a listener to the `MediaQueryListener` that will run a custom callback function in response to the media query status changing.

In older browsers `MediaQueryList` did not yet inherit from [`EventTarget`](../eventtarget), so this method was provided as an alias of [`EventTarget.addEventListener()`](../eventtarget/addeventlistener). Use `addEventListener()` instead of `addListener()` if it is available in the browsers you need to support.

## Syntax

    MediaQueryList.addListener(func)

### Parameters

func  
A function or function reference representing the callback function you want to run when the media query status changes.

### Return value

Void.

## Example

    var paragraph = document.querySelector('p');
    var mediaQueryList = window.matchMedia('(max-width: 600px)');

    function screenTest(e) {
      if (e.matches) {
        /* the viewport is 600 pixels wide or less */
        paragraph.textContent = 'This is a narrow screen — 600px wide or less.';
        document.body.style.backgroundColor = 'pink';
      } else {
        /* the viewport is more than than 600 pixels wide */
        paragraph.textContent = 'This is a wide screen — more than 600px wide.';
        document.body.style.backgroundColor = 'aquamarine';
      }
    }

    mediaQueryList.addListener(screenTest);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-mediaquerylist-addlistener">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'addListener' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`addListener`

9

12

6

10

12.1

5.1

Prior to Safari 14, `MediaQueryList` is based on `EventTarget`, so you must use `addListener()` and `removeListener()` to observe media query lists.

≤37

18

6

Yes

5

Prior to Safari 14, `MediaQueryList` is based on `EventTarget`, so you must use `addListener()` and `removeListener()` to observe media query lists.

1.0

## See also

- [Media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
- [Using media queries from code](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Testing_media_queries)
- [`window.matchMedia()`](../window/matchmedia)
- [`MediaQueryList`](../mediaquerylist)
- [`MediaQueryListEvent`](../mediaquerylistevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList/addListener" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList/addListener</a>
