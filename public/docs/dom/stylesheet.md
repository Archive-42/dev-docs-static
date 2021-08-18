StyleSheet
==========

An object implementing the `StyleSheet` interface represents a single style sheet. CSS style sheets will further implement the more specialized [`CSSStyleSheet`](cssstylesheet) interface.

Properties
----------

[`StyleSheet.disabled`](stylesheet/disabled)  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) representing whether the current stylesheet has been applied or not.

 [`StyleSheet.href`](stylesheet/href) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) representing the location of the stylesheet.

 [`StyleSheet.media`](stylesheet/media) <span class="badge inline readonly">Read only </span>   
Returns a [`MediaList`](medialist) representing the intended destination medium for style information.

 [`StyleSheet.ownerNode`](stylesheet/ownernode) <span class="badge inline readonly">Read only </span>   
Returns a [`Node`](node) associating this style sheet with the current document.

 [`StyleSheet.parentStyleSheet`](stylesheet/parentstylesheet) <span class="badge inline readonly">Read only </span>   
Returns a [`StyleSheet`](stylesheet) including this one, if any; returns `null` if there aren't any.

 [`StyleSheet.title`](stylesheet/title) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) representing the advisory title of the current style sheet.

 [`StyleSheet.type`](stylesheet/type)<span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) representing the style sheet language for this style sheet.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#stylesheet">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'StyleSheet' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Style/">Document Object Model (DOM) Level 2 Style Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/stylesheets.html#StyleSheets-StyleSheet">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'StyleSheet' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`StyleSheet`

1

12

1

9

Yes

1

Yes

Yes

4

Yes

1

Yes

`disabled`

1

12

1

9

Yes

1

Yes

Yes

4

Yes

1

Yes

`href`

1

12

1

9

Yes

1

Yes

Yes

4

Yes

1

Yes

`media`

1

12

1

9

Yes

1

Yes

Yes

4

Yes

1

Yes

`ownerNode`

1

12

1

9

Yes

1

Yes

Yes

4

Yes

1

Yes

`parentStyleSheet`

1

12

1

9

Yes

1

Yes

Yes

4

Yes

1

Yes

`title`

1

12

1

9

Yes

1

Yes

Yes

4

Yes

1

Yes

`type`

1

12

1

9

Yes

1

Yes

Yes

4

Yes

1

Yes

See also
--------

-   [`CSSStyleSheet`](cssstylesheet)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StyleSheet" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StyleSheet</a>
