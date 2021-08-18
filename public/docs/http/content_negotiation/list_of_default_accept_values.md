Content negotiation: List of default Accept values
==================================================

This article documents the default values for the HTTP `Accept` header for specific inputs and browser versions.

Default values
--------------

These are the values sent when the context doesn't give better information. Note that all browsers add the `*/*` MIME Type to cover all cases. This is typically used for requests initiated via the address bar of a browser, or via an HTML [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) element.

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>User Agent</th><th>Value</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td>Firefox</td><td><p><code>text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8</code> (since Firefox 66)<br />
<br />
<code>text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8</code> (in Firefox 65)<br />
<br />
<code>text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8</code> (before)</p></td><td>In Firefox 65 and earlier, this value can be modified using the <a href="http://kb.mozillazine.org/Network.http.accept.default"><code>network.http.accept.default</code></a> parameter. (<a href="https://hg.mozilla.org/mozilla-central/file/tip/modules/libpref/init/all.js#l1750">source)</a></td></tr><tr class="even"><td>Safari, Chrome</td><td><p><code>text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8</code></p></td><td><a href="https://chromium.googlesource.com/chromium/src.git/+/master/services/network/loader_util.cc#24">(source)</a></td></tr><tr class="odd"><td>Safari 5</td><td><p><code>text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8</code></p></td><td>This is an improvement over earlier <code>Accept</code> headers as it no longer ranks <code>image/png</code> above <code>text/html</code></td></tr><tr class="even"><td>Internet Explorer 8</td><td><code>image/jpeg, application/x-ms-application, image/gif, application/xaml+xml, image/pjpeg, application/x-ms-xbap, application/x-shockwave-flash, application/msword, */*</code></td><td>See <a href="https://docs.microsoft.com/en-us/archive/blogs/ieinternals/ie-and-the-accept-header">IE and the Accept Header (IEInternals' MSDN blog)</a>.</td></tr><tr class="odd"><td>Edge</td><td><code>text/html, application/xhtml+xml, image/jxr, */*</code></td><td></td></tr><tr class="even"><td>Opera</td><td><code>text/html, application/xml;q=0.9, application/xhtml+xml, image/png, image/webp, image/jpeg, image/gif, image/x-xbitmap, */*;q=0.1</code></td><td></td></tr></tbody></table>

Values for an image
-------------------

When requesting an image, like through an HTML [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element, user-agent often sets a specific list of media types to be welcomed.

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>User Agent</th><th>Value</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td>Firefox</td><td><p><code>image/webp,*/*</code> (since Firefox 65)<br />
<code>*/*</code> (since Firefox 47)<br />
<code>image/png,image/*;q=0.8,*/*;q=0.5</code> (before)</p></td><td>This value can be modified using the <code>image.http.accept</code> parameter. <a href="https://hg.mozilla.org/mozilla-central/file/tip/modules/libpref/init/all.js#l3779">source</a></td></tr><tr class="even"><td>Safari</td><td><code>image/png,image/svg+xml,image/*;q=0.8,video/*;q=0.8,*/*;q=0.5</code></td><td></td></tr><tr class="odd"><td>Chrome</td><td><code>image/avif,image/webp,image/apng,image/*,*/*;q=0.8</code></td><td><a href="https://chromium.googlesource.com/chromium/src.git/+/master/content/renderer/loader/web_url_loader_impl.cc#99">source</a></td></tr><tr class="even"><td>Internet Explorer 8 or earlier</td><td><code>*/*</code></td><td>See <a href="https://docs.microsoft.com/en-us/archive/blogs/ieinternals/ie-and-the-accept-header">IE and the Accept Header (IEInternals' MSDN blog)</a></td></tr><tr class="odd"><td>Internet Explorer 9</td><td><code>image/png,image/svg+xml,image/*;q=0.8, */*;q=0.5</code></td><td>See <a href="https://docs.microsoft.com/en-us/archive/blogs/fiddler/fiddler-and-the-ie9-release-candidate">Fiddler is better with Internet Explorer 9 (IEInternals' MSDN blog)</a></td></tr></tbody></table>

Values for a video
------------------

When a video is requested, via the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) HTML element, most browsers use specific values.

<table><thead><tr class="header"><th>User Agent</th><th>Value</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td>Firefox earlier than 3.6</td><td><em>no support for <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video"><code>&lt;video&gt;</code></a></em></td><td></td></tr><tr class="even"><td>Firefox 3.6 and later</td><td><code>video/webm,video/ogg,video/*;q=0.9,application/ogg;q=0.7,audio/*;q=0.6,*/*;q=0.5</code></td><td>See <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=489071" class="link-https">bug 489071</a> <a href="https://hg.mozilla.org/mozilla-central/file/tip/dom/html/HTMLVideoElement.cpp#l136">source</a></td></tr><tr class="odd"><td>Chrome</td><td><code>*/*</code></td><td><a href="https://chromium.googlesource.com/chromium/src.git/+/master/services/network/loader_util.cc#27">source</a></td></tr><tr class="even"><td>Internet Explorer 8 or earlier</td><td><em>no support for <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video"><code>&lt;video&gt;</code></a></em></td><td></td></tr></tbody></table>

Values for audio resources
--------------------------

When an audio file is requested, like via the [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) HTML element, most browsers use specific values.

<table><thead><tr class="header"><th>User Agent</th><th>Value</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td>Firefox 3.6 and later</td><td><code>audio/webm,audio/ogg,audio/wav,audio/*;q=0.9,application/ogg;q=0.7,video/*;q=0.6,*/*;q=0.5</code></td><td>See <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=489071" class="link-https">bug 489071</a> <a href="https://hg.mozilla.org/mozilla-central/file/tip/dom/html/HTMLAudioElement.cpp#l81">source</a></td></tr><tr class="even"><td>Safari, Chrome</td><td><code>*/*</code></td><td><a href="https://chromium.googlesource.com/chromium/src.git/+/master/services/network/loader_util.cc#27">source</a></td></tr><tr class="odd"><td>Internet Explorer 8 or earlier</td><td><em>no support for <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio"><code>&lt;audio&gt;</code></a></em></td><td></td></tr><tr class="even"><td>Internet Explorer 9</td><td>?</td><td></td></tr></tbody></table>

Values for scripts
------------------

When a script is requested, like via the [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) HTML element, some browsers use specific values.

<table><thead><tr class="header"><th>User Agent</th><th>Value</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td>Firefox</td><td><code>*/*</code></td><td>See <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=170789" class="link-https">bug 170789</a></td></tr><tr class="even"><td>Safari, Chrome</td><td><code>*/*</code></td><td><a href="https://chromium.googlesource.com/chromium/src.git/+/master/services/network/loader_util.cc#27">source</a></td></tr><tr class="odd"><td>Internet Explorer 8 or earlier</td><td><code>*/*</code></td><td>See <a href="https://docs.microsoft.com/en-us/archive/blogs/ieinternals/ie-and-the-accept-header">IE and the Accept Header (IEInternals' MSDN blog)</a></td></tr><tr class="even"><td>Internet Explorer 9</td><td><code>application/javascript, */*;q=0.8</code></td><td>See <a href="https://docs.microsoft.com/en-us/archive/blogs/fiddler/fiddler-and-the-ie9-release-candidate">Fiddler is better with Internet Explorer 9 (IEInternals' MSDN blog)</a></td></tr></tbody></table>

Values for a CSS stylesheet
---------------------------

When a CSS stylesheet is requested, via the `<link rel="stylesheet">` HTML element, most browsers use specific values.

<table><thead><tr class="header"><th>User Agent</th><th>Value</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td>Firefox 4</td><td><code>text/css,*/*;q=0.1</code></td><td>See <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=170789" class="link-https">bug 170789</a> <a href="https://hg.mozilla.org/mozilla-central/file/tip/layout/style/Loader.cpp#l1548">source</a></td></tr><tr class="even"><td>Internet Explorer 8 or earlier</td><td><code>*/*</code></td><td>See <a href="https://docs.microsoft.com/en-us/archive/blogs/ieinternals/ie-and-the-accept-header">IE and the Accept Header (IEInternals' MSDN blog)</a></td></tr><tr class="odd"><td>Internet Explorer 9</td><td><code>text/css</code></td><td>See <a href="https://docs.microsoft.com/en-us/archive/blogs/fiddler/fiddler-and-the-ie9-release-candidate">Fiddler is better with Internet Explorer 9 (IEInternals' MSDN blog)</a></td></tr><tr class="even"><td>Safari, Chrome</td><td><code>text/css,*/*;q=0.1</code></td><td><a href="https://chromium.googlesource.com/chromium/src.git/+/master/content/renderer/loader/web_url_loader_impl.cc#98">source</a></td></tr><tr class="odd"><td>Opera 11.10</td><td><code>text/html, application/xml;q=0.9, application/xhtml+xml, image/png, image/webp, image/jpeg, image/gif, image/x-xbitmap, */*;q=0.1 </code></td><td></td></tr><tr class="even"><td>Konqueror 4.6</td><td><code>text/css,*/*;q=0.1</code></td><td></td></tr></tbody></table>

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Content_negotiation/List_of_default_Accept_values$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Content_negotiation/List_of_default_Accept_values" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Content_negotiation/List_of_default_Accept_values</a>
