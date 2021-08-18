# Document.lastModified

The `lastModified` property of the [`Document`](../document) interface returns a string containing the date and time on which the current document was last modified.

## Syntax

    var string = document.lastModified;

## Examples

### Simple usage

This example alerts the value of `lastModified`.

    alert(document.lastModified);
    // returns: Tuesday, December 16, 2017 11:09:42

### Transforming lastModified into a Date object

This example transforms `lastModified` into a [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) object.

    let oLastModif = new Date(document.lastModified);

### Transforming lastModified into milliseconds

This example transforms `lastModified` into the number of milliseconds since January 1, 1970, 00:00:00, local time.

    let nLastModif = Date.parse(document.lastModified);

## Notes

Note that as a string, `lastModified` cannot _easily_ be used for comparing the modification dates of documents. Here is a possible example of how to show an alert message when the page changes (see also: [JavaScript cookies API](cookie)):

    if (Date.parse(document.lastModified) > parseFloat(document.cookie.replace(/(?:(?:^|.*;)\s*last_modif\s*\=\s*([^;]*).*$)|^.*$/, "$1") || "0")) {
      document.cookie = "last_modif=" + Date.now() + "; expires=Fri, 31 Dec 9999 23:59:59 GMT; path=" + location.pathname;
      alert("This page has changed!");
    }

…the same example, but skipping the first visit:

    var
      nLastVisit = parseFloat(document.cookie.replace(/(?:(?:^|.*;)\s*last_modif\s*\=\s*([^;]*).*$)|^.*$/, "$1")),
      nLastModif = Date.parse(document.lastModified);

    if (isNaN(nLastVisit) || nLastModif > nLastVisit) {
      document.cookie = "last_modif=" + Date.now() + "; expires=Fri, 31 Dec 9999 23:59:59 GMT; path=" + location.pathname;

      if (isFinite(nLastVisit)) {
        alert("This page has been changed!");
      }
    }

**Note:** WebKit returns the time string in UTC; Gecko and Internet Explorer return a time in the local timezone. (See: [Bug 4363 – document.lastModified returns date in UTC time, but should return it in local time](https://bugs.webkit.org/show_bug.cgi?id=4363))

If you want to know **whether _an external page_ has changed**, please read [this paragraph about the `XMLHttpRequest()` API](../xmlhttprequest/using_xmlhttprequest#get_last_modified_date).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-document-lastmodified">HTML Living Standard<br />
<span class="small">The definition of 'document.lastModified' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`lastModified`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/lastModified" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/lastModified</a>
