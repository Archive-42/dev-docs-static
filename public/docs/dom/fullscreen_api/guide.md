# Guide to the Fullscreen API

This article demonstrates how to use the [Fullscreen API](../fullscreen_api) to place a given element into full-screen mode, as well as how to detect when the browser enters or exits full-screen mode.

## Activating full-screen mode

Given an element that you'd like to present in full-screen mode (such as a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video), for example), you can present it in full-screen mode by calling its [`requestFullscreen()`](../element/requestfullscreen) method.

Let's consider this [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element:

    <video controls id="myvideo">
      <source src="somevideo.webm"></source>
      <source src="somevideo.mp4"></source>
    </video>

We can put that video into full-screen mode as follows:

    var elem = document.getElementById("myvideo");
    if (elem.requestFullscreen) {
      elem.requestFullscreen();
    }

This code checks for the existence of the `requestFullscreen()` method before calling it.

### Presentation differences

It's worth noting a key difference here between the Gecko and WebKit implementations at this time: Gecko automatically adds CSS rules to the element to stretch it to fill the screen: "`width: 100%; height: 100%`". WebKit doesn't do this; instead, it centers the fullscreen element at the same size in a screen that's otherwise black. To get the same fullscreen behavior in WebKit, you need to add your own "`width: 100%; height: 100%;`" CSS rules to the element yourself:

    #myvideo:-webkit-full-screen {
      width: 100%;
      height: 100%;
    }

On the other hand, if you're trying to emulate WebKit's behavior on Gecko, you need to place the element you want to present inside another element, which you'll make fullscreen instead, and use CSS rules to adjust the inner element to match the appearance you want.

### Notification

When fullscreen mode is successfully engaged, the document which contains the element receives a `fullscreenchange` event. When fullscreen mode is exited, the document again receives a `fullscreenchange` event. Note that the `fullscreenchange` event doesn't provide any information itself as to whether the document is entering or exiting fullscreen mode, but if the document has a non null [`fullscreenElement`](../document/fullscreenelement), you know you're in fullscreen mode.

### When a fullscreen request fails

It's not guaranteed that you'll be able to switch into fullscreen mode. For example, [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) elements have the [`allowfullscreen`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-allowfullscreen) attribute in order to opt-in to allowing their content to be displayed in fullscreen mode. In addition, certain kinds of content, such as windowed plug-ins, cannot be presented in fullscreen mode. Attempting to put an element which can't be displayed in fullscreen mode (or the parent or descendant of such an element) won't work. Instead, the element which requested fullscreen will receive a `mozfullscreenerror` event. When a fullscreen request fails, Firefox will log an error message to the Web Console explaining why the request failed. In Chrome and newer versions of Opera however, no such warning is generated.

**Note:** Fullscreen requests need to be called from within an event handler or otherwise they will be denied.

## Getting out of full screen mode

The user always has the ability to exit fullscreen mode of their own accord; see [Things your users want to know](#things_your_users_want_to_know). You can also do so programmatically by calling the [`Document.exitFullscreen()`](../document/exitfullscreen) method.

## Other information

The [`Document`](../document) provides some additional information that can be useful when developing fullscreen web applications:

[`Document.fullscreenElement`](../document/fullscreenelement) / [`ShadowRoot.fullscreenElement`](../shadowroot/fullscreenelement)  
The `fullscreenElement` property tells you the [`Element`](../element) that's currently being displayed fullscreen. If this is non-null, the document (or shadow DOM) is in fullscreen mode. If this is null, the document (or shadow DOM) is not in fullscreen mode.

[`Document.fullscreenEnabled`](../document/fullscreenenabled)  
The `fullscreenEnabled` property tells you whether or not the document is currently in a state that would allow fullscreen mode to be requested.

## Things your users want to know

You'll want to be sure to let your users know that they can press the Esc key (or F11) to exit fullscreen mode.

In addition, navigating to another page, changing tabs, or switching to another application (using, for example, Alt-Tab) while in fullscreen mode exits fullscreen mode as well.

## Example

In this example, a video is presented in a web page. Pressing the Return or Enter key lets the user toggle between windowed and fullscreen presentation of the video.

[View Live Examples](https://media.prod.mdn.mozit.cloud/samples/domref/fullscreen.html)

### Watching for the Enter key

When the page is loaded, this code is run to set up an event listener to watch for the Enter key.

    document.addEventListener("keydown", function(e) {
      if (e.keyCode == 13) {
        toggleFullScreen();
      }
    }, false);

### Toggling fullscreen mode

This code is called when the user hits the Enter key, as seen above.

    function toggleFullScreen() {
      if (!document.fullscreenElement) {
        document.documentElement.requestFullscreen();
      } else {
        if (document.exitFullscreen) {
          document.exitFullscreen();
        }
      }
    }

This starts by looking at the value of the `fullscreenElement` attribute on the [`document`](../document) (checking it prefixed with both `moz`, `ms`, or `webkit`). If it's `null`, the document is currently in windowed mode, so we need to switch to fullscreen mode. Switching to fullscreen mode is done by calling [`element.requestFullscreen()`](../element/requestfullscreen).

If fullscreen mode is already active (`fullscreenElement` is non-`null`), we call [`document.exitFullscreen()`](../document/exitfullscreen).

## Prefixing

**Note:** Currently, only Firefox 64 and Chrome 71 supports this unprefixed.

For the moment not all browsers are implementing the unprefixed version of the API (for vendor agnostic access to the Fullscreen API you can use [Fscreen](https://github.com/rafrex/fscreen)). Here is the table summarizing the prefixes and name differences between them:

<table><thead><tr class="header"><th>Standard</th><th>WebKit (Safari) / Blink (Chrome &amp; Opera) / Edge</th><th>Gecko (Firefox)</th><th>Internet Explorer</th></tr></thead><tbody><tr class="odd"><td><a href="../document/fullscreen"><code>Document.fullscreen</code></a> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>webkitIsFullScreen</code></td><td><code>mozFullScreen</code></td><td>-</td></tr><tr class="even"><td><a href="../document/fullscreenenabled"><code>Document.fullscreenEnabled</code></a></td><td><code>webkitFullscreenEnabled</code></td><td><code>mozFullScreenEnabled</code></td><td><code>msFullscreenEnabled</code></td></tr><tr class="odd"><td><a href="../document/fullscreenelement"><code>Document.fullscreenElement</code></a></td><td><code>webkitFullscreenElement</code></td><td><code>mozFullScreenElement</code></td><td><code>msFullscreenElement</code></td></tr><tr class="even"><td><a href="../document/onfullscreenchange"><code>Document.onfullscreenchange</code></a></td><td><code>onwebkitfullscreenchange</code></td><td><code>onmozfullscreenchange</code></td><td><code>onmsfullscreenchange</code></td></tr><tr class="odd"><td><a href="../document/onfullscreenerror"><code>Document.onfullscreenerror</code></a></td><td><code>onwebkitfullscreenerror</code></td><td><code>onmozfullscreenerror</code></td><td><code>onmsfullscreenerror</code></td></tr><tr class="even"><td><a href="../document/exitfullscreen"><code>Document.exitFullscreen()</code></a></td><td><code>webkitExitFullscreen()</code></td><td><code>mozCancelFullScreen()</code></td><td><code>msExitFullscreen()</code></td></tr><tr class="odd"><td><a href="../element/requestfullscreen"><code>Element.requestFullscreen()</code></a></td><td><code>webkitRequestFullscreen()</code></td><td><code>mozRequestFullScreen()</code></td><td><code>msRequestFullscreen()</code></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fullscreen.spec.whatwg.org/">Fullscreen API</a></td><td><span class="spec-living">Living Standard</span></td><td>Initial version.</td></tr></tbody></table>

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

`Guide`

71

Yes

12

64

10

11

Yes

6

71

Yes

71

Yes

64

10

Yes

6

10.0

Yes

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

`Guide`

71

15

79

≤79

64

9

No

58

15

6

71

≤37

71

18

64

9

50

14

6

10.0

1.0

BCD tables only load in the browser

### Document.fullscreenEnabled

BCD tables only load in the browser

## See also

- [Using fullscreen mode](../fullscreen_api)
- [`Element.requestFullscreen()`](../element/requestfullscreen)
- [`Document.exitFullscreen()`](../document/exitfullscreen)
- [`Document.fullscreen`](../document/fullscreen)
- [`Document.fullscreenElement`](../document/fullscreenelement)
- [`:fullscreen`](https://developer.mozilla.org/en-US/docs/Web/CSS/:fullscreen), [`::backdrop`](https://developer.mozilla.org/en-US/docs/Web/CSS/::backdrop)
- [`allowfullscreen`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-allowfullscreen)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API/Guide" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API/Guide</a>
