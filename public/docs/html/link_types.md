Link types
==========

In HTML, link types indicate the relationship between two documents, in which one links to the other using an [`<a>`](element/a), [`<area>`](element/area), [`<form>`](element/form), or [`<link>`](element/link) element.

<table><caption>List of the defined link types and their significance in HTML</caption><colgroup><col style="width: 25%" /><col style="width: 25%" /><col style="width: 25%" /><col style="width: 25%" /></colgroup><thead><tr class="header"><th>Link Type</th><th>Description</th><th>Allowed in these elements</th><th>Not allowed in these elements</th></tr></thead><tbody><tr class="odd"><td><code>alternate</code></td><td><ul><li>If the element is <a href="element/link"><code>&lt;link&gt;</code></a> and the <a href="element/link#attr-rel"><code>rel</code></a> attribute also contains the <code>stylesheet</code> type, the link defines an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Alternative_style_sheets">alternative style sheet</a>; in that case the <a href="element/link#attr-title"><code>title</code></a> attribute must be present and not be the empty string.</li><li>If the <a href="element/link#attr-type"><code>type</code></a> is set to <code>application/rss+xml</code> or <code>application/atom+xml</code>, the link defines a <a href="https://developer.mozilla.org/en-US/docs/Archive/RSS/Getting_Started/Syndicating">syndication feed</a>. The first one defined on the page is the default.</li><li>Otherwise, the link defines an alternative page, of one of these types:<ul><li>for another medium, like a handheld device (if the <a href="element/link#attr-media"><code>media</code></a> attribute is set)</li><li>in another language (if the <a href="element/link#attr-hreflang"><code>hreflang</code></a> attribute is set),</li><li>in another format, such as a PDF (if the <a href="element/link#attr-type"><code>type</code></a> attribute is set)</li><li>a combination of these</li></ul></li></ul></td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="even"><td><code>archives</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td>Defines a hyperlink to a document that contains an archive link to this one. For example, a blog entry could link to a monthly index page this way.<br />
<br />
<strong>Note:</strong> Although recognized, the singular <code>archive</code> is incorrect and must be avoided.</td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="odd"><td><code>author</code></td><td>Defines a hyperlink to a page describing the author or providing a way to contact the author.<br />
<br />
<strong>Note:</strong> This may be a <code>mailto:</code> hyperlink, but this is not recommended on public pages as robot harvesters will quickly lead to a lot of spam sent to the address. In that case, it is better to lead to a page containing a contact form.<br />
<br />
Although recognized, the <a href="element/link#attr-rev"><code>rev</code></a> attribute on <a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a> or<a href="element/link"><code>&lt;link&gt;</code></a> elements with a link type of <code>made</code> is incorrect and should be replaced by the <a href="element/link#attr-rel"><code>rel</code></a> attribute with this link type.</td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="even"><td><code>bookmark</code></td><td>Indicates that the hyperlink is a <a href="https://developer.mozilla.org/en-US/docs/Permalink">permalink</a> for the nearest ancestor <a href="element/article"><code>&lt;article&gt;</code></a> element. If none, it is a permalink for the <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines">section</a> that the element is most closely associated to.<br />
<br />
This allows for bookmarking a single article in a page containing multiple articles, such as on a monthly summary blog page, or a blog aggregator.</td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a></td><td><a href="element/link"><code>&lt;link&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="odd"><td><code>canonical</code></td><td>From Wikipedia, the free encyclopedia: <a href="https://en.wikipedia.org/wiki/Canonical_link_element">Canonical_link_element</a><br />
A canonical link element is an HTML element that helps webmasters prevent duplicate content issues by specifying the "canonical" or "preferred" version of a web page as part of search engine optimization.</td><td><a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="even"><td><code>dns-prefetch</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td>Hints to the browser that a resource is needed, allowing the browser to do a DNS lookup and protocol handshaking before a user clicks the link.</td><td><a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="odd"><td><code>external</code></td><td>Indicates that the hyperlink leads to a resource outside the site of the current page; that is, following the link will make the user leave the site.</td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td><td><a href="element/link"><code>&lt;link&gt;</code></a></td></tr><tr class="even"><td><code>first</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td>Indicates that the hyperlink leads to the first resource of the <em>sequence</em> the current page is in.<br />
<br />
<strong>Note:</strong> Other link types related to linking resources in the same sequence are <code>last</code>, <code>prev</code>, <code>next</code>.<br />
<br />
Although recognized, the synonyms <code>begin</code> and <code>start</code> are incorrect and must be avoided.</td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="odd"><td><code>help</code></td><td><ul><li>If the element is <a href="element/a"><code>&lt;a&gt;</code></a> or <a href="element/area"><code>&lt;area&gt;</code></a>, it indicates that the hyperlink leads to a resource giving further help about the parent of the element, and its descendants.</li><li>If the element is <a href="element/link"><code>&lt;link&gt;</code></a> it indicates that the hyperlink leads to a resource giving further help about the page as a whole.</li></ul></td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a>, <a href="element/link"><code>&lt;link&gt;</code></a></td><td><em>None.</em></td></tr><tr class="even"><td><code>icon</code></td><td>Defines a resource for representing the page in the user interface, usually an icon (auditory or visual). In the browser, it is usually referred to as the <a href="https://developer.mozilla.org/en-US/docs/Glossary/Favicon">favicon</a>.<br />
<br />
If there are multiple <code>&lt;link rel="icon"&gt;</code>s, the browser uses their <a href="element/link#attr-media"><code>media</code></a>, <a href="element/link#attr-type"><code>type</code></a>, and <a href="element/link#attr-sizes"><code>sizes</code></a> attributes to select the most appropriate icon. If several icons are equally appropriate, the last one is used. If the most appropriate icon is later found to be inappropriate, for example because it uses an unsupported format, the browser proceeds to the next-most appropriate, and so on.<br />
<br />
<strong>Note:</strong> Apple's iOS does not use this link type, nor the <a href="element/link#attr-sizes"><code>sizes</code></a> attribute, like others mobile browsers do, to select a webpage icon for Web Clip or a start-up placeholder. Instead it uses the non-standard <a href="https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html#//apple_ref/doc/uid/TP40002051-CH3-SW4"><code>apple-touch-icon</code></a> and <a href="https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html#//apple_ref/doc/uid/TP40002051-CH3-SW6"><code>apple-touch-startup-image</code></a> respectively.<br />
<br />
The <code>shortcut</code> link type is often seen before <code>icon</code>, but this link type is non-conforming, ignored and <strong>web authors must not use it anymore</strong>.</td><td><a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="odd"><td><code>import</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Web_Components/HTML_Imports">HTML Imports</a></td><td><a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="even"><td><code>index</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td>Indicates that the page is part of a <em>hierarchical</em> structure and that the hyperlink leads to the top level resource of that structure.<br />
<br />
If one or several <code>up</code> link types are also present, the number of these <code>up</code> indicates the depth of the current page in the hierarchy.</td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="odd"><td><code>last</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td>Indicates that the hyperlink leads to the <em>last</em> resource of the <em>sequence</em> the current page is in.<br />
<br />
<strong>Note:</strong> Other link types related to linking resources in the same sequence are <code>first</code>, <code>prev</code>, <code>next</code>.<br />
<br />
Although recognized, the synonym <code>end</code> is incorrect and must be avoided.</td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="even"><td><code>license</code></td><td>Indicates that the hyperlink leads to a document describing the licensing information. If not inside the <a href="element/head"><code>&lt;head&gt;</code></a> element, the standard doesn't distinguish between a hyperlink applying to a specific part of the document or to the document as a whole. Only the data on the page can indicate this.<br />
<br />
<strong>Note:</strong> Although recognized, the synonym <code>copyright</code> is incorrect and must be avoided.</td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a>, <a href="element/link"><code>&lt;link&gt;</code></a></td><td><em>None.</em></td></tr><tr class="odd"><td><code>manifest</code></td><td>Indicates that the linked file is a <a href="https://developer.mozilla.org/en-US/docs/Web/Manifest">Web App Manifest</a>.</td><td><a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="even"><td><code>modulepreload</code></td><td>Initiates early (and high-priority) loading of module scripts.</td><td><a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="odd"><td><code>next</code></td><td>Indicates that the hyperlink leads to the <em>next</em> resource of the <em>sequence</em> the current page is in.<br />
<br />
<strong>Note:</strong> Other link types related to linking resources in the same sequence are <code>first</code>, <code>prev</code>, <code>last</code>.</td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a>, <a href="element/link"><code>&lt;link&gt;</code></a></td><td><em>None.</em></td></tr><tr class="even"><td><code>nofollow</code></td><td>Indicates that the linked document is not endorsed by the author of this one, for example if it has no control over it, if it is a bad example or if there is commercial relationship between the two (sold link). This link type may be used by some search engines that use popularity ranking techniques.</td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td><td><a href="element/link"><code>&lt;link&gt;</code></a></td></tr><tr class="odd"><td><code>noopener</code></td><td><p>Instructs the browser to open the link without granting the new browsing context access to the document that opened it — by not setting the <a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/opener"><code>Window.opener</code></a> property on the opened window (it returns <code>null</code>).<br />
<br />
This is especially useful when opening untrusted links, in order to ensure they cannot tamper with the originating document via the <a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/opener"><code>Window.opener</code></a> property (see <a href="https://mathiasbynens.github.io/rel-noopener/">About rel=noopener</a> for more details), while still providing the <code>Referer</code> HTTP header (unless <code>noreferrer</code> is used as well).</p><p>Note that when <code>noopener</code> is used, nonempty target names other than <code>_top</code>, <code>_self</code>, and <code>_parent</code> are all treated like <code>_blank</code> in terms of deciding whether to open a new window/tab.</p></td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td><td><a href="element/link"><code>&lt;link&gt;</code></a></td></tr><tr class="even"><td><code>noreferrer</code></td><td><p>Prevents the browser, when navigating to another page, to send this page address, or any other value, as referrer via the <code>Referer:</code> HTTP header.<br />
(In Firefox, before Firefox 37, this worked only in links found in pages. Links clicked in the UI, like "Open in a new tab" via the contextual menu, ignored this).</p></td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td><td><a href="element/link"><code>&lt;link&gt;</code></a></td></tr><tr class="odd"><td><code>opener</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td><p>Reverts implicit <code>rel="noopener"</code> addition on links with <code>target="_blank"</code> (See <a href="https://github.com/whatwg/html/issues/4078">related HTML spec discussion</a>, <a href="https://trac.webkit.org/changeset/237144/webkit/">WebKit change</a>, and <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=1503681">Firefox bug discussion</a>).</p></td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td><td><a href="element/link"><code>&lt;link&gt;</code></a></td></tr><tr class="even"><td><code>pingback</code></td><td>Defines an external resource URI to call if one wishes to make a comment or a citation about the webpage. The protocol used to make such a call is defined in the <a href="https://www.hixie.ch/specs/pingback/pingback">Pingback 1.0</a> specification.<br />
<br />
<strong>Note:</strong> if the <code>X-Pingback:</code> HTTP header is also present, it supersedes the <a href="element/link"><code>&lt;link&gt;</code></a> element with this link type.</td><td><a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="odd"><td><code>preconnect</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td>Provides a hint to the browser suggesting that it open a connection to the linked web site in advance, without disclosing any private information or downloading any content, so that when the link is followed the linked content can be fetched more quickly.</td><td><a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="even"><td><code>prefetch</code></td><td>Suggests that the browser fetch the linked resource in advance, as it is likely to be requested by the user. Starting with Firefox 44, the value of the <a href="element/link#attr-crossorigin"><code>crossorigin</code></a> attribute is taken into consideration, making it possible to make anonymous prefetches.<br />
<br />
<strong>Note:</strong> The <a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Link_prefetching_FAQ">Link Prefetch FAQ</a> has details on which links can be prefetched and on alternative methods.</td><td><a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="odd"><td><code>preload</code></td><td>Tells the browser to download a resource because this resource will be needed later during the current navigation. See <a href="preloading_content">Preloading content with rel="preload"</a> for more details.</td><td><a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="even"><td><code>prerender</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td>Suggests that the browser fetch the linked resource in advance, and that it also render the prefetched content offscreen so it can be quickly presented to the user once needed.</td><td><a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="odd"><td><code>prev</code></td><td>Indicates that the hyperlink leads to the <em>preceding</em> resource of the <em>sequence</em> the current page is in.<br />
<br />
<strong>Note:</strong> You can also use the <code>next</code> keyword to specify a link to the next page in the sequence.<br />
<br />
Although recognized, the synonym <code>previous</code> is incorrect and must be avoided.</td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/link"><code>&lt;link&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td><td><em>None.</em></td></tr><tr class="even"><td><code>search</code></td><td>Indicates that the hyperlink references a document whose interface is specially designed for searching in this document, or site, and its resources.<br />
<br />
If the <a href="element/link#attr-type"><code>type</code></a> attribute is set to <code>application/opensearchdescription+xml </code>the resource is an <a href="https://developer.mozilla.org/en-US/docs/Web/OpenSearch">OpenSearch plugin</a> that can be easily added to the interface of some browsers like Firefox or Internet Explorer.</td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/link"><code>&lt;link&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td><td><em>None.</em></td></tr><tr class="odd"><td><code>shortlink</code></td><td><a href="https://code.google.com/archive/p/shortlink/wikis/Specification.wiki"><code>shortlink</code> Specification</a><br />
From Wikipedia, the free encyclopedia: <a href="https://en.wikipedia.org/wiki/URL_shortening">URL shortening</a><br />
Some websites create short links to make sharing links via instant messaging easier.</td><td><a href="element/link"><code>&lt;link&gt;</code></a></td><td>???</td></tr><tr class="even"><td><code>sidebar</code> <span class="icon non-standard" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This API has not been standardized. </span><span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td>Indicates that the hyperlink leads to a resource that would be better suited for a secondary browsing context, like a <em>sidebar</em>. Browsers, that don't have such a context will ignore this keyword.<br />
<br />
While once part of the HTML specification, this has been removed from the spec and is only implemented by versions of Firefox prior to Firefox 63.</td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="odd"><td><code>stylesheet</code></td><td>Defines an external resource to be used as a stylesheet. If the <code>type</code> is not set, the browser should assume it is a <code>text/css</code> stylesheet until further inspection.<br />
<br />
If used in combination with the <code>alternate</code> keyword, it defines an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Alternative_style_sheets">alternative style sheet</a>; in that case the <a href="element/link#attr-title"><code>title</code></a> attribute must be present and not be the empty string.</td><td><a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="even"><td><code>tag</code></td><td>Indicates that the hyperlink refers to a document describing a <em>tag</em> that applies to this document.<br />
<br />
<strong>Note:</strong> This link type should not be set on links to a member of a tag cloud as these do not apply to a single document but to a set of pages.</td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a></td><td><a href="element/link"><code>&lt;link&gt;</code></a>, <a href="element/form"><code>&lt;form&gt;</code></a></td></tr><tr class="odd"><td><code>up</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td>Indicates that the page is part of a <em>hierarchical</em> structure and that the hyperlink leads to the higher level resource of that structure.<br />
<br />
The number of <code>up</code> link types indicates the depth difference between the current page and the linked resource.</td><td><a href="element/a"><code>&lt;a&gt;</code></a>, <a href="element/area"><code>&lt;area&gt;</code></a>, <a href="element/link"><code>&lt;link&gt;</code></a></td><td><a href="element/form"><code>&lt;form&gt;</code></a></td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/preload/#x2.link-type-preload">Preload<br />
<span class="small">The definition of 'preload' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added <code>preload</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/resource-hints/#dfn-preconnect">Resource Hints<br />
<span class="small">The definition of 'preconnect' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added <code>dns-prefetch</code>, <code>preconnect</code>, and <code>prerender</code> values.</td></tr><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/links.html#linkTypes">HTML Living Standard<br />
<span class="small">The definition of 'link types' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added <code>opener</code> and made <code>noopener</code> the default behavior for <code>target="_blank"</code> links.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/links.html#linkTypes">HTML5<br />
<span class="small">The definition of 'link types' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added <code>tag</code>, <code>search</code>, <code>prefetch</code>, <code>noreferrer</code>, <code>nofollow</code>, <code>icon</code>, and <code>author</code>.<br />
Renamed <code>copyright</code> to <code>license</code>.<br />
Removed <code>start</code>, <code>chapter</code>, <code>section</code>, <code>subsection</code>, and <code>appendix</code></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/types.html#type-links">HTML 4.01 Specification<br />
<span class="small">The definition of 'link types' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added <code>alternate</code>, <code>stylesheet</code>, <code>start</code>, <code>chapter</code>, <code>section</code>, <code>subsection</code>, <code>appendix</code>, and <code>bookmark</code>.<br />
Renamed <code>previous</code> to <code>prev</code>.<br />
Removed <code>top</code>, and <code>search</code>.</td></tr><tr class="even"><td><a href="about:unknown#link">Unknown<br />
<span class="small">The definition of '&lt;link&gt;' in that specification.</span></a></td><td>Obsolete</td><td>Added <code>top</code>, <code>contents</code>, <code>index</code>, <code>glossary</code>, <code>copyright</code>, <code>next</code>, <code>previous</code>, <code>help</code>, and <code>search</code>.</td></tr><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc1866">RFC 1866: HTML 2.0</a></td><td>Obsolete</td><td>Initial definition.</td></tr></tbody></table>

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

`Link_types`

1

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`alternate_stylesheet`

1-48

?

3

8

Yes

?

?

?

4

?

?

?

`dns-prefetch`

46

≤79

3

?

33

?

46

Yes

4

?

?

Yes

`icon`

4

If both ICO and PNG are available, will use ICO over PNG if ICO has better matching sizes set. (Per caniuse.com.).

12

In version 79 and later (Blink-based Edge), if both ICO and PNG are available, will use ICO over PNG if ICO has better matching sizes set. (Per caniuse.com.)

2

Before Firefox 83, the `crossorigin` attribute is not supported for `rel="icon"`.

11

9

In version 15 and later (Blink-based Opera), if both ICO and PNG are available, will use ICO over PNG if ICO has better matching sizes set. (Per caniuse.com.)

3.1

If both ICO and PNG are available, will ALWAYS use ICO file, regardless of sizes set. (Per caniuse.com.)

38

18

4

No

No

Does not use favicons at all (but may have alternative for bookmarks, etc.). (Per caniuse.com.)

4.0

`manifest`

No

No

?

?

No

?

39

39

?

?

?

4.0

`modulepreload`

66

≤79

?

?

53

?

66

66

?

47

?

9.0

`preconnect`

46

79

39

Before Firefox 41, it doesn't obey the `crossorigin` attribute.

No

33

11.1

46

46

39

Before Firefox 41, it doesn't obey the `crossorigin` attribute.

33

11.3

4.0

`prefetch`

8

12

2

11

15

No

4.4

18

4

14

No

1.5

`preload`

50

Doesn’t support `as="audio"`, `as="audioworklet"`, `as="document"`, `as="embed"`, `as="manifest"`, `as="object"`, `as="paintworklet"`, `as="report"`, `as="sharedworker"`, `as="video"`, `as="worker"`, or `as="xslt"`.

≤79

Doesn’t support `as="audio"`, `as="audioworklet"`, `as="document"`, `as="embed"`, `as="manifest"`, `as="object"`, `as="paintworklet"`, `as="report"`, `as="sharedworker"`, `as="video"`, `as="worker"`, or `as="xslt"`.

85

78

56-57

Disabled due to various web compatibility issues (e.g. [bug 1405761](https://bugzil.la/1405761)).

?

37

?

50

`as="document"` is unsupported. See [bug 593267](https://crbug.com/593267).

50

Doesn’t support `as="audio"`, `as="audioworklet"`, `as="document"`, `as="embed"`, `as="manifest"`, `as="object"`, `as="paintworklet"`, `as="report"`, `as="sharedworker"`, `as="video"`, `as="worker"`, or `as="xslt"`.

85

79

56-57

Disabled due to various web compatibility issues (e.g. [bug 1405761](https://bugzil.la/1405761)).

?

?

5.0

`as="document"` is unsupported. See [bug 593267](https://crbug.com/593267).

`prerender`

13

79

No

11

15

No

4.4

18

No

14

No

1.5

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types</a>
