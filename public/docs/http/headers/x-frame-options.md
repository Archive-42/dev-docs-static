X-Frame-Options
===============

The `X-Frame-Options` [HTTP](../index) response header can be used to indicate whether or not a browser should be allowed to render a page in a [`<frame>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frame), [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe), [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed) or [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object). Sites can use this to avoid [click-jacking](https://developer.mozilla.org/en-US/docs/Web/Security/Types_of_attacks#Click-jacking) attacks, by ensuring that their content is not embedded into other sites.

The added security is provided only if the user accessing the document is using a browser that supports `X-Frame-Options`.

**Note:** The [`Content-Security-Policy`](content-security-policy) HTTP header has a [`frame-ancestors`](content-security-policy/frame-ancestors) directive which [obsoletes](https://www.w3.org/TR/CSP2/#frame-ancestors-and-frame-options) this header for supporting browsers.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

There are two possible directives for `X-Frame-Options`:

    X-Frame-Options: DENY
    X-Frame-Options: SAMEORIGIN

### Directives

If you specify `DENY`, not only will attempts to load the page in a frame fail when loaded from other sites, attempts to do so will fail when loaded from the same site. On the other hand, if you specify `SAMEORIGIN`, you can still use the page in a frame as long as the site including it in a frame is the same as the one serving the page.

`DENY`  
The page cannot be displayed in a frame, regardless of the site attempting to do so.

`SAMEORIGIN`  
The page can only be displayed in a frame on the same origin as the page itself. The spec leaves it up to browser vendors to decide whether this option applies to the top level, the parent, or the whole chain, although it is argued that the option is not very useful unless all ancestors are also in the same origin (see [bug 725490](https://bugzilla.mozilla.org/show_bug.cgi?id=725490)). Also see [Browser compatibility](#Browser_compatibility) for support details.

 `ALLOW-FROM uri`   
This is an obsolete directive that no longer works in modern browsers. Don't use it. In supporting legacy browsers, a page can be displayed in a frame only on the specified origin *uri*. Note that in the legacy Firefox implementation this still suffered from the same problem as `SAMEORIGIN` did — it doesn't check the frame ancestors to see if they are in the same origin. The [`Content-Security-Policy`](content-security-policy) HTTP header has a [`frame-ancestors`](content-security-policy/frame-ancestors) directive which you can use instead.

Examples
--------

**Note:** Setting X-Frame-Options inside the [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) element is useless! For instance, `<meta http-equiv="X-Frame-Options" content="deny">` has no effect. Do not use it! `X-Frame-Options` works only by setting through the HTTP header, as in the examples below.

### Configuring Apache

To configure Apache to send the `X-Frame-Options` header for all pages, add this to your site's configuration:

    Header always set X-Frame-Options "SAMEORIGIN"

To configure Apache to set the `X-Frame-Options` DENY, add this to your site's configuration:

    Header set X-Frame-Options "DENY"

### Configuring nginx

To configure nginx to send the `X-Frame-Options` header, add this either to your http, server or location configuration:

    add_header X-Frame-Options SAMEORIGIN always;

### Configuring IIS

To configure IIS to send the `X-Frame-Options` header, add this to your site's `Web.config` file:

    <system.webServer>
      ...

      <httpProtocol>
        <customHeaders>
          <add name="X-Frame-Options" value="SAMEORIGIN" />
        </customHeaders>
      </httpProtocol>

      ...
    </system.webServer>

Or see this [Microsoft support article on setting this configuration using the IIS Manager](https://support.office.com/en-us/article/Mitigating-framesniffing-with-the-X-Frame-Options-header-1911411b-b51e-49fd-9441-e8301dcdcd79) user interface.

### Configuring HAProxy

To configure HAProxy to send the `X-Frame-Options` header, add this to your front-end, listen, or backend configuration:

    rspadd X-Frame-Options:\ SAMEORIGIN

Alternatively, in newer versions:

    http-response set-header X-Frame-Options SAMEORIGIN

### Configuring Express

To configure Express to send the `X-Frame-Options` header, you can use [helmet](https://helmetjs.github.io/) which uses [frameguard](https://helmetjs.github.io/docs/frameguard/) to set the header. Add this to your server configuration:

    const helmet = require('helmet');
    const app = express();
    app.use(helmet.frameguard({ action: 'SAMEORIGIN' }));

Alternatively, you can use frameguard directly:

    const frameguard = require('frameguard')
    app.use(frameguard({ action: 'SAMEORIGIN' }))

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7034">RFC 7034</a></td><td>HTTP Header Field X-Frame-Options</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`X-Frame-Options`

4

12

3.6.9

8

10.5

4

ALLOW-FROM

No

12 — 79

18 — 70

8

No

No

SAMEORIGIN

Yes

 Yes   
Starting in Chrome 61, this applies to all of a frame's ancestors.

12

Yes

 Yes   
Starting in Firefox 59, this applies to all of a frame's ancestors.

8

Yes

 Yes   
Starting in Opera 48, this applies to all of a frame's ancestors.

Yes

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`X-Frame-Options`

Yes

Yes

Yes

Yes

Yes

Yes

ALLOW-FROM

No

No

18

?

No

No

SAMEORIGIN

Yes

 Yes   
Starting in Chrome 61, this applies to all of a frame's ancestors.

Yes

 Yes   
Starting in Chrome 61, this applies to all of a frame's ancestors.

Yes

 Yes   
Starting in Firefox 59, this applies to all of a frame's ancestors.

Yes

 Yes   
Starting in Opera 48, this applies to all of a frame's ancestors.

?

Yes

See also
--------

-   [`Content-Security-Policy`](content-security-policy) directive [`frame-ancestors`](content-security-policy/frame-ancestors)
-   [HTTP Header Field X-Frame-Options - RFC 7034](https://tools.ietf.org/html/rfc7034)
-   [ClickJacking Defenses - IEBlog](https://docs.microsoft.com/en-us/archive/blogs/ie/ie8-security-part-vii-clickjacking-defenses)
-   [Combating ClickJacking with X-Frame-Options - IEInternals](https://docs.microsoft.com/en-us/archive/blogs/ieinternals/combating-clickjacking-with-x-frame-options)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options</a>
