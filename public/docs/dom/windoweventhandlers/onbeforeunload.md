WindowEventHandlers.onbeforeunload
==================================

The `onbeforeunload` property of the [`WindowEventHandlers`](../windoweventhandlers) mixin is the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `beforeunload` events. These events fire when a window is about to `unload` its resources. At this point, the document is still visible and the event is still cancelable.

**Note:** To combat unwanted pop-ups, some browsers don't display prompts created in `beforeunload` event handlers unless the page has been interacted with. Moreover, some don't display them at all.

**Note**: You shouldn't use the `beforeunload` event with `sendBeacon()`. See the `Navigator.sendBeacon()` page for more details and best practices.

Syntax
------

    window.addEventListener("beforeunload", function(event) { ... });
    window.onbeforeunload = function(event) { ... };

Typically, it is better to use [`window.addEventListener()`](../eventtarget/addeventlistener) and the `beforeunload` event, instead of `onbeforeunload`.

Example
-------

This example prompts the user before unloading.

The HTML specification states that authors should use the [`Event.preventDefault()`](../event/preventdefault) method instead of using [`Event.returnValue`](../event/returnvalue) to prompt the user.

    window.addEventListener('beforeunload', function (e) {
      // Cancel the event
      e.preventDefault(); // If you prevent default behavior in Mozilla Firefox prompt will always be shown
      // Chrome requires returnValue to be set
      e.returnValue = '';
    });

Guarantee the browser unload by removing the *returnValue* property of the event

    window.addEventListener('beforeunload', function (e) {
      // the absence of a returnValue property on the event will guarantee the browser unload happens
      delete e['returnValue'];
    });

Notes
-----

When your page uses JavaScript to render content, the JavaScript may stop when leaving and then navigating back to the page. You can bind to `window.onbeforeunload` to prevent the browser from fully caching the page. If you do so, JavaScript in the page will be triggered on the subsequent return visit and update the content as desired.

Specifications
--------------

The event was originally introduced by Microsoft in Internet Explorer 4 and standardized in the HTML5 specification.

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-window-onbeforeunload">HTML Living Standard<br />
<span class="small">The definition of 'onbeforeunload' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/#windoweventhandlers">HTML 5.1<br />
<span class="small">The definition of 'GlobalEventHandlers' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/#windoweventhandlers">HTML5<br />
<span class="small">The definition of 'GlobalEventHandlers' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`onbeforeunload`

1

12

1

4

12

3

1

18

4

12

1

1.0

`custom_text_support`

Yes-51

No

Yes-44

Yes

Yes-38

Yes-9

Yes-51

Yes-51

Yes-44

Yes-41

No

Yes-5.0

The HTML specification states that authors should use the [`Event.preventDefault()`](../event/preventdefault) method instead of using [`Event.returnValue`](../event/returnvalue) to prompt the user. However, this is not yet supported by all browsers.

When this event returns (or sets the `returnValue` property to) a value other than `null` or `undefined`, the user will be prompted to confirm the page unload. In older browsers, the return value of the event is displayed in this dialog. Starting with Firefox 44, Chrome 51, Opera 38, and Safari 9.1, a generic string not under the control of the webpage will be shown instead of the returned string. For example:

-   Firefox displays the string, "This page is asking you to confirm that you want to leave - data you have entered may not be saved." (see [bug 588292](https://bugzilla.mozilla.org/show_bug.cgi?id=588292)).
-   Chrome displays the string, "Do you want to leave this site? Changes you made may not be saved." (see [Chrome Platform Status](https://www.chromestatus.com/feature/5349061406228480)).

Internet Explorer does not respect the `null` return value and will display this to users as "null" text. You have to use `undefined` to skip the prompt.

In some browsers, calls to [`window.alert()`](../window/alert), [`window.confirm()`](../window/confirm), and [`window.prompt()`](../window/prompt) may be ignored during this event. See the [HTML specification](https://www.w3.org/TR/html5/webappapis.html#user-prompts) for more details.

Note also, that various browsers ignore the result of the event and do not ask the user for confirmation at all. In such cases, the document will always be unloaded automatically. Firefox has a switch named `dom.disable_beforeunload` in *about:config* to enable this behavior. As of Chrome 60, the confirmation [will be skipped](https://www.chromestatus.com/feature/5082396709879808) if the user has not performed a gesture in the frame or page since it was loaded. Pressing F5 in the page seems to count as user interaction, whereas mouse-clicking the refresh arrow or pressing F5 with Chrome DevTools focused does not count as user interaction (as of Chrome 81).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onbeforeunload" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onbeforeunload</a>
