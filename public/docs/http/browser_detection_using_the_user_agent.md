Browser detection using the user agent
======================================

Serving different Web pages or services to different browsers is usually a bad idea. The Web is meant to be accessible to everyone, regardless of which browser or device they're using. There are ways to develop your website to progressively enhance itself based on the availability of features rather than by targeting specific browsers.

But browsers and standards are not perfect, and there are still some edge cases where detecting the browser is needed. Using the user agent to detect the browser looks simple, but doing it well is, in fact, a very hard problem. This document will guide you in doing this as correctly as possible.

It's worth re-iterating: it's very rarely a good idea to use user agent sniffing. You can almost always find a better, more broadly compatible way to solve your problem!

Considerations before using browser detection
---------------------------------------------

When considering using the user agent string to detect which browser is being used, your first step is to try to avoid it if possible. Start by trying to identify **why** you want to do it.

Are you trying to work around a specific bug in some version of a browser?  
Look, or ask, in specialized forums: you're unlikely to be the first to hit this problem. Also, experts, or simply people with another point of view, can give you ideas for working around the bug. If the problem seems uncommon, it's worth checking if this bug has been reported to the browser vendor via their bug tracking system (<a href="https://bugzilla.mozilla.org" class="link-https">Mozilla</a>; [WebKit](https://bugs.webkit.org); [Blink](https://www.chromium.org/issue-tracking); <a href="https://bugs.opera.com/" class="link-https">Opera</a>). Browser makers do pay attention to bug reports, and the analysis may hint about other workarounds for the bug.

Are you trying to check for the existence of a specific feature?  
Your site needs to use a specific Web feature that some browsers don't yet support, and you want to send those users to an older Web site with fewer features but that you know will work. This is the worst reason to use user agent detection because odds are eventually all the other browsers will catch up. In addition, it is not practical to test every one of the less popular browsers and test for them. You should **never** do user agent sniffing. There is **always** the alternative of doing feature detection instead.

<!-- -->

Do you want to provide different HTML depending on which browser is being used?  
This is usually a bad practice, but there are some cases in which this is necessary. In these cases, you should first analyze your situation to be sure it's really necessary. Can you prevent it by adding some non-semantic [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) or [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) elements? The difficulty of successfully using user agent detection is worth a few disruptions to the purity of your HTML. Also, rethink your design: can you use progressive enhancement or fluid layouts to help remove the need to do this?

Avoiding user agent detection
-----------------------------

If you want to avoid using user agent detection, you have options!

Feature detection  
Feature detection is where you don't try to figure out which browser is rendering your page, but instead, you check to see if the specific feature you need is available. If it's not, you use a fallback. In those rare cases where behavior differs between browsers, instead of checking the user agent string, you should instead implement a test to detect how the browser implements the API and determine how to use it from that. An example of feature detection is as follows. In 2017, Chrome [unflagged experimental lookbehind support in regular expressions](https://www.chromestatus.com/feature/5668726032564224), but no other browser supported it. So, you might have thought to do this:

    // this code snippet splits a string in a special notation

    if (navigator.userAgent.indexOf("Chrome") !== -1){
        // YES! The user is suspected to support look-behind regexps
        // DO NOT USE /(?<=[A-Z])/. It will cause a syntax error in
        //  browsers that do not support look-behind expressions
        //  because all browsers parse the entire script, including
        //  sections of the code that are never executed.
        var camelCaseExpression = new RegExp("(?<=[A-Z])"); 
        var splitUpString = function(str) {
            return (""+str).split(camelCaseExpression);
        };
    } else {
        /*This fallback code is much less performant, but works*/
        var splitUpString = function(str){
            return str.replace(/[A-Z]/g,"z$1").split(/z(?=[A-Z])/g);
        };
    }
    console.log(splitUpString("fooBare")); // ["fooB", "are"]
    console.log(splitUpString("jQWhy")); // ["jQ", "W", "hy"]

The above code would have made several incorrect assumptions:

-   It assumed that all user agent strings that include the substring "Chrome" are Chrome. UA strings are notoriously misleading.
-   It assumed that the lookbehind feature would always be available if the browser was Chrome. The agent might be an older version of Chrome, from before support was added, or (because the feature was experimental at the time) it could be a later version of Chrome that removed it.
-   Most importantly, it assumed no other browsers would support the feature. Support could have been added to other browsers at any time, but this code would have continued choosing the inferior path.

Problems like these can be avoided by testing for support of the feature itself instead:

    var isLookBehindSupported = false;

    try {
        new RegExp("(?<=)");
        isLookBehindSupported = true;
    } catch (err) {
        // If the agent doesn't support lookbehinds, the attempted
        // creation of a RegExp object using that syntax throws and
        // isLookBehindSupported remains false.
    }

    var splitUpString = isLookBehindSupported ? function(str) {
        return (""+str).split(new RegExp("(?<=[A-Z])"));
    } : function(str) {
        return str.replace(/[A-Z]/g,"z$1").split(/z(?=[A-Z])/g);
    };

As the above code demonstrates, there is **always** a way to test browser support without user agent sniffing. There is **never** any reason to check the user agent string for this.

Lastly, the above code snippets bring about a critical issue with cross-browser coding that must always be taken into account. Don't unintentionally use the API you are testing for in unsupported browsers. This may sound obvious and simple, but sometimes it is not. For example, in the above code snippets, using lookbehind in short-regexp notation (e.g. /reg/igm) will cause a parser error in unsupported browsers. Thus, in the above example, you would use *new RegExp("(?&lt;=look\_behind\_stuff)");* instead of */(?&lt;=look\_behind\_stuff)/*, even in the lookbehind supported section of your code.

Progressive enhancement  
This design technique involves developing your Web site in 'layers', using a bottom-up approach, starting with a simpler layer and improving the capabilities of the site in successive layers, each using more features.

Graceful degradation  
This is a top-down approach in which you build the best possible site using all the features you want, then tweak it to make it work on older browsers. This can be harder to do, and less effective, than progressive enhancement, but may be useful in some cases.

Mobile device detection  
Arguably the most common use and misuse of user agent sniffing is to detect if the device is a mobile device. However, people too often overlook what they are really after. People use user agent sniffing to detect if the users' device is touch-friendly and has a small screen so they can optimize their website accordingly. While user agent sniffing can sometimes detect these, not all devices are the same: some mobile devices have big screen sizes, some desktops have a small touchscreen, some people use smart TV's which are an entirely different ballgame altogether, and some people can dynamically change the width and height of their screen by flipping their tablet on its side! So, user agent sniffing is definitely not the way to go. Thankfully, there are much better alternatives. Use [Navigator.maxTouchPoints](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/maxTouchPoints) to detect if the user's device has a touchscreen. Then, default back to checking the user agent screen only *if (!("maxTouchPoints" in navigator)) { /\*Code here\*/}*. Using this information of whether the device has a touchscreen, do not change the entire layout of the website just for touch devices: you will only create more work and maintenance for yourself. Rather, add in touch conveniences such as bigger, more easily clickable buttons (you can do this using CSS by simply increasing the font size). Here is an example of code that increases the padding of \#exampleButton to 1em on mobile devices.

    var hasTouchScreen = false;
    if ("maxTouchPoints" in navigator) { 
        hasTouchScreen = navigator.maxTouchPoints > 0;
    } else if ("msMaxTouchPoints" in navigator) {
        hasTouchScreen = navigator.msMaxTouchPoints > 0; 
    } else {
        var mQ = window.matchMedia && matchMedia("(pointer:coarse)");
        if (mQ && mQ.media === "(pointer:coarse)") {
            hasTouchScreen = !!mQ.matches;
        } else if ('orientation' in window) {
            hasTouchScreen = true; // deprecated, but good fallback
        } else {
            // Only as a last resort, fall back to user agent sniffing
            var UA = navigator.userAgent;
            hasTouchScreen = (
                /\b(BlackBerry|webOS|iPhone|IEMobile)\b/i.test(UA) ||
                /\b(Android|Windows Phone|iPad|iPod)\b/i.test(UA)
            );
        }
    }
    if (hasTouchScreen)
        document.getElementById("exampleButton").style.padding="1em";

As for the screen size, simply use *window.innerWidth* and window.addEventListener("resize", function(){ /\*refresh screen size dependent things\*/ }). What you want to do for screen size is not slash off information on smaller screens. That will only annoy people because it will force them to use the desktop version. Rather, try to have fewer columns of information in a longer page on smaller screens while having more columns with a shorter page on larger screen sizes. This effect can be easily achieved using CSS [flexboxes](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox), sometimes with [floats](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats) as a partial fallback.

Also try to move less relevant/important information down to the bottom and group the page's content together meaningfully. Although it is off-topic, perhaps the following detailed example might give you insights and ideas that persuade you to forgo user agent sniffing. Let us imagine a page composed of boxes of information; each box is about a different feline breed or canine breed. Each box has an image, an overview, and a historical funfact. The pictures are kept to a maximum reasonable size even on large screens. For the purposes of grouping the content meaningfully, all the cat boxes are separated from all the dog boxes such that the cat and dog boxes are not intermixed together. On a large screen, it saves space to have multiple columns to reduce the space wasted to the left and to the right of the pictures. The boxes can be separated into multiple columns via two equally fair method. From this point on, we shall assume that all the dog boxes are at the top of the source code, that all the cat boxes are at the bottom of the source code, and that all these boxes have the same parent element. There a single instance of a dog box immediately above a cat box, of course. The first method uses horizontal [Flexboxes](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox) to group the content such that when the page is displayed to the end user, all the dogs boxes are at the top of the page and all the cat boxes are lower on the page. The second method uses a [Column](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Column_layouts) layout and resents all the dogs to the left and all the cats to the right. Only in this particular scenario, it is appropriate to provide no fallback for the flexboxes/multicolumns, resulting in a single column of very wide boxes on old browsers. Also consider the following. If more people visit the webpage to see the cats, then it might be a good idea to put all the cats higher in the source code than the dogs so that more people can find what they are looking for faster on smaller screens where the content collapses down to one column.

Next, always make your code dynamic. The user can flip their mobile device on its side, changing the width and height of the page. Or, there might be some weird flip-phone-like device thing in the future where flipping it out extends the screen. Do not be the developer having a headache over how to deal with the flip-phone-like device thing. Never be satisfied with your webpage until you can open up the dev tools side panel and resize the screen while the webpage looks smooth, fluid, and dynamically resized. The simplest way to do this is to separate all the code that moves content around based on screen size to a single function that is called when the page is loaded and at each [resize](https://developer.mozilla.org/en-US/docs/Web/API/Window/resize_event) event thereafter. If there is a lot calculated by this layout function before it determines the new layout of the page, then consider debouncing the event listener such that it is not called as often. Also note that there is a huge difference between the media queries `(max-width: 25em)`, `not all and (min-width: 25em)`, and `(max-width: 24.99em)`: `(max-width: 25em)` excludes `(max-width: 25em)`, whereas `not all and (min-width: 25em)` includes `(max-width: 25em)`. `(max-width: 24.99em)` is simply a poor man's version of `not all and (min-width: 25em)`: do not use `(max-width: 24.99em)` because the layout *might* break on very high font sizes on very high definition devices in the future. Always be very deliberate about choosing the right media query and choosing the right &gt;=, &lt;=, &gt;, or &lt; in any corresponding JavaScript because it is very easy to get these mixed up, resulting in the website looking wonking right at the screen size where the layout changes. Thus, thoroughly test the website at the exact widths/heights where layout changes occur to ensure that the layout changes occur properly.

Making the best of user agent sniffing
--------------------------------------

After reviewing all of the above better alternatives to user agent sniffing, there are still some potential cases where user agent sniffing is appropriate and justified.

One such case is using user agent sniffing as a fallback when detecting if the device has a touch screen. See the [Mobile Device Detection](#Mobile_Device_Detection) section for more information.

Another such case is for fixing bugs in browsers that do not automatically update. Internet Explorer (on Windows) and Webkit (on iOS) are two perfect examples. Prior to version 9, Internet Explorer had unbelievable issues with rendering bugs, CSS bugs, API bugs, and so forth. However, Internet Explorer was such a special little <s>wasp</s> exception prior to version 9 that it was very easy to detect the browser based upon the browser-specific features available. Webkit is a bit worse because Apple forces all of the browsers on IOS to use Webkit internally, thus the user has no way to get a better more updated browser on older devices. Most bugs can be detected, but some bugs take more effort to detect than others. In such cases, it might be beneficial to use user agent sniffing to save on performance. For example, Webkit 6 has a bug whereby when the device orientation changes, the browser might not fire [MediaQueryList](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList) listeners when it should. To overcome this bug, observe the code below.

    var UA=navigator.userAgent, isWebkit=/\b(iPad|iPhone|iPod)\b/.test(UA) &&
                   /WebKit/.test(UA) && !/Edge/.test(UA) && !window.MSStream;

    var mediaQueryUpdated = true, mqL = [];
    function whenMediaChanges(){mediaQueryUpdated = true}

    var listenToMediaQuery = isWebkit ? function(mQ, f) {
        if(/height|width/.test(mQ.media)) mqL.push([mQ, f]);
        mQ.addListener(f), mQ.addListener(whenMediaChanges);
    } : function(){};
    var destroyMediaQuery = isWebkit ? function(mQ) {
        for (var i=0,len=mqL.length|0; i<len; i=i+1|0)
            if (mqL[i][0] === mQ) mqL.splice(i, 1);
        mQ.removeListener(whenMediaChanges);
    } : listenToMediaQuery;
            
    var orientationChanged = false;
    addEventListener("orientationchange", function(){
        orientationChanged = true;
    }, PASSIVE_LISTENER_OPTION);

    addEventListener("resize", setTimeout.bind(0,function(){
        if (orientationChanged && !mediaQueryUpdated)
            for (var i=0,len=mqL.length|0; i<len; i=i+1|0)
                mqL[i][1]( mqL[i][0] );
        mediaQueryUpdated = orientationChanged = false;
    },0));

Which part of the user agent contains the information you are looking for?
--------------------------------------------------------------------------

As there is no uniformity of the different part of the user agent string, this is the tricky part.

### Browser Name

When people say they want "browser detection", often they actually want "rendering engine detection". Do you actually want to detect Firefox, as opposed to SeaMonkey, or Chrome as opposed to Chromium? Or do you actually simply want to see if the browser is using the Gecko or the WebKit rendering engine? If this is what you need, see further down the page.

Most browsers set the name and version in the format *BrowserName/VersionNumber*, with the notable exception of Internet Explorer. But as the name is not the only information in a user agent string that is in that format, you can not discover the name of the browser, you can only check if the name you are looking for. But note that some browsers are lying: Chrome for example reports both as Chrome and Safari. So to detect Safari you have to check for the Safari string and the absence of the Chrome string, Chromium often reports itself as Chrome too or Seamonkey sometimes reports itself as Firefox.

Also, pay attention not to use a simple regular expression on the BrowserName, user agents also contain strings outside the Keyword/Value syntax. Safari & Chrome contain the string 'like Gecko', for instance.

<table><colgroup><col style="width: 25%" /><col style="width: 25%" /><col style="width: 25%" /><col style="width: 25%" /></colgroup><thead><tr class="header"><th></th><th>Must contain</th><th>Must not contain</th><th></th></tr></thead><tbody><tr class="odd"><td>Firefox</td><td>Firefox/xyz</td><td>Seamonkey/xyz</td><td></td></tr><tr class="even"><td>Seamonkey</td><td>Seamonkey/xyz</td><td></td><td></td></tr><tr class="odd"><td>Chrome</td><td>Chrome/xyz</td><td>Chromium/xyz</td><td></td></tr><tr class="even"><td>Chromium</td><td>Chromium/xyz</td><td></td><td></td></tr><tr class="odd"><td>Safari</td><td>Safari/xyz</td><td>Chrome/xyz or Chromium/xyz</td><td>Safari gives two version numbers: one technical in the Safari/xyz token, and one user-friendly in a Version/xyz token</td></tr><tr class="even"><td>Opera</td><td><p>OPR/xyz <sup>[1]</sup></p><p>Opera/xyz</p></td><td></td><td><p><sup>[1]</sup> Opera 15+ (Blink-based engine)</p><p><sup>[2]</sup> Opera 12- (Presto-based engine)</p></td></tr><tr class="odd"><td>Internet Explorer</td><td><p>; MSIE xyz; <sup>[1]</sup></p><p>Trident/7.0; .*rv:xyz <sup>[2]</sup></p></td><td></td><td><p><sup>[1]</sup> Internet Explorer 10-</p><p><sup>[2]</sup> Internet Explorer 11</p></td></tr></tbody></table>

Of course, there is absolutely no guarantee that another browser will not hijack some of these things (like Chrome hijacked the Safari string in the past). That's why browser detection using the user agent string is unreliable and should be done only with the check of the version number (hijacking of past versions is less likely).

### Browser version

The browser version is often, but not always, put in the value part of the *BrowserName/VersionNumber* token in the User Agent String. This is of course not the case for Internet Explorer (which puts the version number right after the MSIE token), and for Opera after version 10, which has added a Version/*VersionNumber* token.

Here again, be sure to take the right token for the browser you are looking for, as there is no guarantee that others will contain a valid number.

### Rendering engine

As seen earlier, in most cases, looking for the rendering engine is a better way to go. This will help to not exclude lesser known browsers. Browsers sharing a common rendering engine will display a page in the same way: it is often a fair assumption that what will work in one will work in the other.

There are five major rendering engines: Trident, Gecko, Presto, Blink, and WebKit. As sniffing the rendering engines names is common, a lot of user agents added other rendering names to trigger detection. It is therefore important to pay attention not to trigger false-positives when detecting the rendering engine.

<table><thead><tr class="header"><th></th><th>Must contain</th><th></th></tr></thead><tbody><tr class="odd"><td>Gecko</td><td>Gecko/xyz</td><td></td></tr><tr class="even"><td>WebKit</td><td>AppleWebKit/xyz</td><td>Pay attention, WebKit browsers add a 'like Gecko' string that may trigger false positive for Gecko if the detection is not careful.</td></tr><tr class="odd"><td>Presto</td><td>Opera/xyz</td><td><strong>Note:</strong> Presto is no longer used in Opera browser builds &gt;= version 15 (see 'Blink')</td></tr><tr class="even"><td>Trident</td><td>Trident/xyz</td><td>Internet Explorer put this token in the <em>comment</em> part of the User Agent String</td></tr><tr class="odd"><td>EdgeHTML</td><td>Edge/xyz</td><td>The non-Chromium Edge puts its engine version after the <em>Edge/</em> token, not the application version.<br />
<strong>Note:</strong> EdgeHTML is no longer used in Edge browser builds &gt;= version 79 (see 'Blink').</td></tr><tr class="even"><td>Blink</td><td>Chrome/xyz</td><td></td></tr></tbody></table>

Rendering engine version
------------------------

Most rendering engines put the version number in the *RenderingEngine/VersionNumber* token, with the notable exception of Gecko. Gecko puts the Gecko version number in the comment part of the User Agent after the `rv:` string. From Gecko 14 for the mobile version and Gecko 17 for the desktop version, it also puts this value in the `Gecko/version` token (previous version put there the build date, then a fixed date called the GeckoTrail).

OS
--

The Operating System is given in most User Agent strings (although not web-focused platforms like Firefox OS), but the format varies a lot. It is a fixed string between two semi-colons, in the comment part of the User Agent. These strings are specific for each browser. They indicate the OS, but also often its version and information on the relying hardware (32 or 64 bits, or Intel/PPC for Mac).

Like in all cases, these strings may change in the future, one should use them only in conjunction with the detection of already released browsers. A technological survey must be in place to adapt the script when new browser versions are coming out.

### Mobile, Tablet or Desktop

The most common reason to perform user agent sniffing is to determine which type of device the browser runs on. The goal is to serve different HTML to different device types.

-   Never assume that a browser or a rendering engine only runs on one type of device. Especially don't make different defaults for different browsers or rendering engines.
-   Never use the OS token to define if a browser is on mobile, tablet or desktop. The OS may run on more than one type of (for example, Android runs on tablets as well as phones).

The following table summarizes the way major browser vendors indicate that their browsers are running on a mobile device:

<table><caption>Common browsers User Agent strings</caption><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Browser</th><th>Rule</th><th>Example</th></tr></thead><tbody><tr class="odd"><td>Mozilla (Gecko, Firefox)</td><td><a href="https://developer.mozilla.org/en-US/docs/Gecko_user_agent_string_reference"><strong>Mobile</strong> or <strong>Tablet</strong> token</a> in the comment.</td><td>Mozilla/5.0 (Android; Mobile; rv:13.0) Gecko/13.0 Firefox/13.0</td></tr><tr class="even"><td>WebKit-based (Android, Safari)</td><td><a href="https://developer.apple.com/library/safari/documentation/AppleApplications/Reference/SafariWebContent/OptimizingforSafarioniPhone/OptimizingforSafarioniPhone.html#//apple_ref/doc/uid/TP40006517-SW3"><strong>Mobile Safari</strong> token</a> outside the comment.</td><td>Mozilla/5.0 (Linux; U; Android 4.0.3; de-ch; HTC Sensation Build/IML74K) AppleWebKit/534.30 (KHTML, like Gecko) Version/4.0 Mobile Safari/534.30</td></tr><tr class="odd"><td>Blink-based (Chromium, Google Chrome, Opera 15+, Edge on Android)</td><td><a href="https://developers.google.com/chrome/mobile/docs/user-agent"><strong>Mobile Safari</strong> token</a> outside the comment.</td><td>Mozilla/5.0 (Linux; Android 4.4.2); Nexus 5 Build/KOT49H) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/33.0.1750.117 Mobile Safari/537.36 OPR/20.0.1396.72047</td></tr><tr class="even"><td>Presto-based (Opera 12-)</td><td><p><a href="http://my.opera.com/community/openweb/idopera/"><strong>Opera Mobi/xyz</strong> token</a> in the comment (Opera 12-)</p></td><td><p>Opera/9.80 (Android 2.3.3; Linux; Opera Mobi/ADR-1111101157; U; es-ES) Presto/2.9.201 Version/11.50</p></td></tr><tr class="odd"><td>Internet Explorer</td><td><strong>IEMobile/xyz</strong> token in the comment.</td><td>Mozilla/5.0 (compatible; MSIE 9.0; Windows Phone OS 7.5; Trident/5.0; IEMobile/9.0)</td></tr><tr class="even"><td>Edge on Windows 10 Mobile</td><td><strong>Mobile/xyz</strong> &amp; <strong>Edge/</strong> tokens outside the comment.</td><td>Mozilla/5.0 (Windows Phone 10.0; Android 6.0.1; Xbox; Xbox One) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Mobile Safari/537.36 Edge/16.16299</td></tr></tbody></table>

In summary, we recommend looking for the string “Mobi” anywhere in the User Agent to detect a mobile device.

If the device is large enough that it's not marked with “Mobi”, you should serve your desktop site (which, as a best practice, should support touch input anyway, as more desktop machines are appearing with touchscreens).

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Browser_detection_using_the_user_agent$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Browser_detection_using_the_user_agent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Browser_detection_using_the_user_agent</a>