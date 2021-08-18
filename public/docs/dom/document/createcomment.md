# Document.createComment()

`createComment()` creates a new comment node, and returns it.

## Syntax

    CommentNode = document.createComment(data);

### Parameters

data  
A string containing the data to be added to the Comment.

## Example

    var docu = new DOMParser().parseFromString('<xml></xml>',  'application/xml');
    var comment = docu.createComment('This is a not-so-secret comment in your document');

    docu.getElementsByTagName('xml')[0].appendChild(comment);

    alert(new XMLSerializer().serializeToString(docu));
    // Displays: <xml><!--This is a not-so-secret comment in your document--></xml>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-createcomment">DOM<br />
<span class="small">The definition of 'document.createComment' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`createComment`

1

12

1

6

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/createComment" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/createComment</a>
