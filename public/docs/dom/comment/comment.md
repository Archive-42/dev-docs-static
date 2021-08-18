# Comment()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Comment()` constructor returns a newly created [`Comment`](../comment) object with the optional [`DOMString`](../domstring) given in parameter as its textual content.

## Syntax

    comment1 = new Comment(); // Create an empty comment
    comment2 = new Comment("This is a comment");

## Example

    var comment = new Comment("Test");

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-comment-comment">DOM<br />
<span class="small">The definition of 'Comment: Comment' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`Comment`

29

16

24

No

16

7

≤37

29

24

16

7

2.0

**Note**: For browsers where this constructor is not supported, [`Document.createComment()`](../document/createcomment) may be suitable.

## See also

- [The DOM interfaces index](../document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Comment/Comment" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Comment/Comment</a>
