Feature Policy
==============

Feature Policy allows web developers to selectively enable, disable, and modify the behavior of certain features and APIs in the browser. It is similar to [Content Security Policy](https://developer.mozilla.org/en-US/docs/Glossary/CSP) but controls features instead of security behavior.

The `Feature-Policy` header has now been renamed to `Permissions-Policy` in the spec, and this article will eventually be updated to reflect that change.

In a nutshell
-------------

Feature Policy provides a mechanism to explicitly declare what functionality is used (or not used), throughout your website. This allows you to lock in best practices, even as the codebase evolves over time — as well as to more safely compose third-party content — by limiting which features are available.

With Feature Policy, you opt-in to a set of "policies" for the browser to enforce on specific features used throughout a website. These policies restrict what APIs the site can access or modify the browser's default behavior for certain features.

Examples of what you can do with Feature Policy:

-   Change the default behavior of autoplay on mobile and third party videos.
-   Restrict a site from using sensitive APIs like camera or microphone.
-   Allow iframes to use the [fullscreen API](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API).
-   Block the use of outdated APIs like [synchronous XHR](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest) and [`document.write()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/write).
-   Ensure images are sized properly and are not too big for the viewport.

Concepts and usage
------------------

Feature Policy allows you to control which origins can use which features, both in the top-level page and in embedded frames. Essentially, you write a policy, which is an allowed list of origins for each feature. For every feature controlled by Feature Policy, the feature is only enabled in the current document or frame if its origin matches the allowed list of origins.

For each policy-controlled feature, the browser maintains a list of origins for which the feature is enabled, known as an allowlist. If you do not specify a policy for a feature, then a default allowlist will be used. The default allowlist is specific to each feature.

### Writing a policy

A policy is described using a set of individual policy directives. A policy directive is a combination of a defined feature name, and an allowlist of origins that can use the feature.

### Specifying your policy

Feature Policy provides two ways to specify policies to control features:

-   The [`Feature-Policy`](headers/feature-policy) HTTP header.
-   The [`allow`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#Attributes) attribute on iframes.

The primary difference between the HTTP header and the `allow` attribute is that the allow attribute only controls features within an iframe. The header controls features in the response and any embedded content within the page.

For more details see [Using Feature Policy](feature_policy/using_feature_policy).

### Inferring the policy

Scripts can programatically query information about the feature policy via the [`FeaturePolicy`](https://developer.mozilla.org/en-US/docs/Web/API/FeaturePolicy) object located at either [`Document.featurePolicy`](https://developer.mozilla.org/en-US/docs/Web/API/Document/featurePolicy) or [`HTMLIFrameElement.featurePolicy`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement/featurePolicy).

Types of policy-controlled features
-----------------------------------

Though Feature Policy provides control of multiple features using a consistent syntax, the behavior of policy controlled features varies and depends on several factors.

The general principle is that there should be an intuitive or non-breaking way for web developers to detect or handle the case when the feature is disabled. Newly introduced features may have an explicit API to signal the state. Existing features that later integrate with Feature Policy will typically use existing mechanisms. Some approaches include:

-   Return "permission denied" for JavaScript APIs that require user permission grants.
-   Return `false` or error from an existing JavaScript API that provides access to feature.
-   Change the default values or options that control the feature behavior.

The current set of policy-controlled features fall into two broad categories:

-   Enforcing best practices for good user experiences.
-   Providing granular control over sensitive or powerful features.

### Best practices for good user experiences

There are several policy-controlled features to help enforce best practices for providing good performance and user experiences.

In most cases, the policy-controlled features represent functionality that when used will negatively impact the user experience. To avoid breaking existing web content, the default for such policy-controlled features is to allow the functionality to be used by all origins. Best practices are then enforced by using policies that disable the policy-controlled features. For more details see "Enforcing best practices for good user experiences".

The features include:

-   Layout-inducing animations
-   Legacy image formats
-   Oversized images
-   Synchronous scripts
-   Synchronous XMLHTTPRequest
-   Unoptimized images
-   Unsized media

### Granular control over certain features

The web provides functionality and APIs that may have privacy or security risks if abused. In some cases, you may wish to strictly limit how such functionality is used on a website. There are policy-controlled features to allow functionality to be enabled/disabled for specific origins or frames within a website. Where available, the feature integrates with the Permissions API, or feature-specific mechanisms to check if the feature is available.

The features include (see [Features list](headers/feature-policy#Directives)):

-   Accelerometer
-   Ambient light sensor
-   Autoplay
-   Camera
-   Encrypted media
-   Fullscreen
-   Geolocation
-   Gyroscope
-   Magnetometer
-   Microphone
-   Midi
-   PaymentRequest
-   Picture-in-picture
-   USB
-   Web Share API
-   VR / XR

Examples
--------

-   [Using Feature Policy](feature_policy/using_feature_policy)
-   See [Feature Policy Demos](http://feature-policy-demos.appspot.com/) for example usage of many policies.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-permissions-policy/#feature-policy-http-header-field">Permissions Policy<br />
<span class="small">The definition of 'Feature-Policy' in that specification.</span></a></td><td><span class="spec-ED">Editor's Draft</span></td><td>Initial definition. Defines the <a href="headers/feature-policy"><code>Feature-Policy</code></a> header. Directives are defined in the specs for the features they control. See individual directive pages for details.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

[`Feature-Policy`](headers/feature-policy)

60

79

74

74

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

47

11.1

11.1   
Only supported through the `allow` attribute on `<iframe>` elements.

[`accelerometer`](headers/feature-policy/accelerometer)

69

Disabled

69

Disabled

Disabled From version 69: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

79

Disabled

79

Disabled

Disabled From version 79: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

56

Disabled

56

Disabled

Disabled From version 56: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

[`ambient-light-sensor`](headers/feature-policy/ambient-light-sensor)

69

Disabled

69

Disabled

Disabled From version 69: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

79

Disabled

79

Disabled

Disabled From version 79: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

56

Disabled

56

Disabled

Disabled From version 56: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

[`autoplay`](headers/feature-policy/autoplay)

64

79

74

74

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

51

No

[`battery`](headers/feature-policy/battery)

No

 No   
Will be implemented, see [bug 1007264](https://crbug.com/1007264).

No

 No   
Will be implemented, see [bug 1007264](https://crbug.com/1007264).

No

No

No

No

[`camera`](headers/feature-policy/camera)

60

79

74

74

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

48

11.1

[`display-capture`](headers/feature-policy/display-capture)

No

No

74

74

67

Disabled

Disabled From version 67: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

No

No

[`document-domain`](headers/feature-policy/document-domain)

77

79

74

74

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

64

No

[`encrypted-media`](headers/feature-policy/encrypted-media)

60

79

74

74

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

48

No

[`fullscreen`](headers/feature-policy/fullscreen)

62

79

74

74

Before Firefox 80, applying `fullscreen` to an `<iframe>` (i.e. via the `allow` attribute) does not work unless the `allowfullscreen` attribute is also present.

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

49

No

[`geolocation`](headers/feature-policy/geolocation)

60

79

74

74

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

47

No

[`gyroscope`](headers/feature-policy/gyroscope)

69

Disabled

69

Disabled

Disabled From version 69: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

79

Disabled

79

Disabled

Disabled From version 79: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

56

Disabled

56

Disabled

Disabled From version 56: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

[`layout-animations`](headers/feature-policy/layout-animations)

No

No

No

No

No

No

[`legacy-image-formats`](headers/feature-policy/legacy-image-formats)

68

Disabled

68

Disabled

Disabled From version 68: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

79

Disabled

79

Disabled

Disabled From version 79: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

55

Disabled

55

Disabled

Disabled From version 55: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

[`magnetometer`](headers/feature-policy/magnetometer)

69

Disabled

69

Disabled

Disabled From version 69: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

79

Disabled

79

Disabled

Disabled From version 79: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

56

Disabled

56

Disabled

Disabled From version 56: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

[`microphone`](headers/feature-policy/microphone)

60

79

74

74

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

48

11.1

[`midi`](headers/feature-policy/midi)

60

79

74

74

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

47

No

[`oversized-images`](headers/feature-policy/oversized-images)

72

Disabled

72

Disabled

Disabled From version 72: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

79

Disabled

79

Disabled

Disabled From version 79: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

60

Disabled

60

Disabled

Disabled From version 60: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

[`payment`](headers/feature-policy/payment)

60

79

74

74

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

47

No

[`picture-in-picture`](headers/feature-policy/picture-in-picture)

No

No

No

No

No

No

[`publickey-credentials-get`](headers/feature-policy/publickey-credentials-get)

84

84

No

No

No

No

[`sync-xhr`](headers/feature-policy/sync-xhr)

65

79

No

No

52

No

[`unoptimized-images`](headers/feature-policy/unoptimized-images)

72

Disabled

72

Disabled

Disabled From version 72: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

79

Disabled

79

Disabled

Disabled From version 79: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

60

Disabled

60

Disabled

Disabled From version 60: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

[`unsized-media`](headers/feature-policy/unsized-media)

66

Disabled

66

Disabled

Disabled From version 66: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

79

Disabled

79

Disabled

Disabled From version 79: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

53

Disabled

53

Disabled

Disabled From version 53: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

[`usb`](headers/feature-policy/usb)

60

79

No

No

47

No

[`vibrate`](headers/feature-policy/vibrate)

No

No

No

No

No

No

[`vr`](headers/feature-policy/vr)

62 — 80

62 — 80   
WebVR API was never enabled by default in any production builds and was replaced by WebXR Device API.

79 — 80

79 — 80   
WebVR API was never enabled by default in any production builds and was replaced by WebXR Device API.

No

No

49 — 67

49 — 67   
WebVR API was never enabled by default in any production builds and was replaced by WebXR Device API.

No

[`wake-lock`](headers/feature-policy/wake-lock)

No

No

No

No

No

No

[`xr-spatial-tracking`](headers/feature-policy/xr-spatial-tracking)

79

79

No

No

66

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

[`Feature-Policy`](headers/feature-policy)

60

60

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

44

11.3

11.3   
Only supported through the `allow` attribute on `<iframe>` elements.

8.0

[`accelerometer`](headers/feature-policy/accelerometer)

No

69

Disabled

69

Disabled

Disabled From version 69: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

48

Disabled

48

Disabled

Disabled From version 48: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

[`ambient-light-sensor`](headers/feature-policy/ambient-light-sensor)

No

69

Disabled

69

Disabled

Disabled From version 69: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

48

Disabled

48

Disabled

Disabled From version 48: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

[`autoplay`](headers/feature-policy/autoplay)

64

64

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

47

No

9.0

[`battery`](headers/feature-policy/battery)

No

No

 No   
Will be implemented, see [bug 1007264](https://crbug.com/1007264).

No

No

No

No

[`camera`](headers/feature-policy/camera)

60

60

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

45

11.3

8.0

[`display-capture`](headers/feature-policy/display-capture)

No

No

67

Disabled

67

Disabled

Disabled From version 67: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

No

No

[`document-domain`](headers/feature-policy/document-domain)

No

No

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

No

No

[`encrypted-media`](headers/feature-policy/encrypted-media)

60

60

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

45

No

8.0

[`fullscreen`](headers/feature-policy/fullscreen)

62

62

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

46

No

8.0

[`geolocation`](headers/feature-policy/geolocation)

60

60

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

44

No

8.0

[`gyroscope`](headers/feature-policy/gyroscope)

No

69

Disabled

69

Disabled

Disabled From version 69: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

48

Disabled

48

Disabled

Disabled From version 48: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

[`layout-animations`](headers/feature-policy/layout-animations)

No

No

No

No

No

No

[`legacy-image-formats`](headers/feature-policy/legacy-image-formats)

No

68

Disabled

68

Disabled

Disabled From version 68: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

48

Disabled

48

Disabled

Disabled From version 48: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

[`magnetometer`](headers/feature-policy/magnetometer)

No

69

Disabled

69

Disabled

Disabled From version 69: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

48

Disabled

48

Disabled

Disabled From version 48: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

[`microphone`](headers/feature-policy/microphone)

60

60

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

45

11.3

8.0

[`midi`](headers/feature-policy/midi)

60

60

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

44

No

8.0

[`oversized-images`](headers/feature-policy/oversized-images)

No

72

Disabled

72

Disabled

Disabled From version 72: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

50

Disabled

50

Disabled

Disabled From version 50: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

[`payment`](headers/feature-policy/payment)

60

60

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

44

No

8.0

[`picture-in-picture`](headers/feature-policy/picture-in-picture)

No

No

No

No

No

No

[`publickey-credentials-get`](headers/feature-policy/publickey-credentials-get)

84

84

No

No

No

No

[`sync-xhr`](headers/feature-policy/sync-xhr)

65

65

No

47

No

9.0

[`unoptimized-images`](headers/feature-policy/unoptimized-images)

No

72

Disabled

72

Disabled

Disabled From version 72: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

50

Disabled

50

Disabled

Disabled From version 50: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

[`unsized-media`](headers/feature-policy/unsized-media)

No

66

Disabled

66

Disabled

Disabled From version 66: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

47

Disabled

47

Disabled

Disabled From version 47: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

9.0

[`usb`](headers/feature-policy/usb)

60

60

No

44

No

8.0

[`vibrate`](headers/feature-policy/vibrate)

No

No

No

No

No

No

[`vr`](headers/feature-policy/vr)

No

62 — 80

62 — 80   
WebVR API was never enabled by default in any production builds and was replaced by WebXR Device API.

No

46 — ?

46 — ?   
WebVR API was never enabled by default in any production builds and was replaced by WebXR Device API.

No

8.0 — ?

8.0 — ?   
WebVR API was never enabled by default in any production builds and was replaced by WebXR Device API.

[`wake-lock`](headers/feature-policy/wake-lock)

No

No

No

No

No

No

[`xr-spatial-tracking`](headers/feature-policy/xr-spatial-tracking)

No

79

No

No

No

No

See also
--------

-   [Using Feature Policy](feature_policy/using_feature_policy)
-   [`Feature-Policy`](headers/feature-policy) HTTP header
-   [`allow`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#Attributes) attribute on iframes
-   [Introduction to Feature Policy](https://developers.google.com/web/updates/2018/06/feature-policy)
-   [Feature policies on www.chromestatus.com](https://www.chromestatus.com/features#component%3A%20Blink%3EFeaturePolicy)
-   [Feature-Policy Tester (Chrome Developer Tools extension)](https://chrome.google.com/webstore/detail/feature-policy-tester-dev/pchamnkhkeokbpahnocjaeednpbpacop)
-   [Privacy, permissions, and information security](https://developer.mozilla.org/en-US/docs/Web/Privacy)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy</a>
