HTMLElement.accessKeyLabel
==========================

The `HTMLElement.accessKeyLabel` read-only property returns a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) containing the element's browser-assigned access key (if any); otherwise it returns an empty string.

Syntax
------

    label = element.accessKeyLabel

Example
-------

### JavaScript

    var btn = document.getElementById('btn1');
    var shortcutLabel = btn.accessKeyLabel || btn.accessKey;
    btn.title += ' [' + shortcutLabel.toUpperCase() + ']';

    btn.onclick = function () {
      var feedback = document.createElement('output');
      feedback.textContent = 'Pressed!';
      btn.insertAdjacentElement('afterend', feedback);
    };

### HTML

    <button accesskey="h" title="Caption" id="btn1">Hover me</button>

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dom-accesskeylabel">HTML Living Standard<br />
<span class="small">The definition of 'HTMLElement.accessKeyLabel' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from initial definition.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/">HTML 5.1</a></td><td><span class="spec-rec">Recommendation</span></td><td>Removed. <a href="https://github.com/w3c/html/pull/144">pull w3c/html#144</a>, <a href="https://github.com/w3c/html/issues/99">issue w3c/html#99</a>, <a href="https://discourse.wicg.io/t/accesskeylabel-author-accessible-info-about-shortcuts/1392/3">WICG discussion</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/editing.html#dom-accesskeylabel">HTML5<br />
<span class="small">The definition of 'HTMLElement.accessKeyLabel' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>, initial definition.</td></tr></tbody></table>

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

`accessKeyLabel`

No

No

8

No

No

14

No

No

8

No

14

No

See also
--------

-   [`HTMLElement.accessKey`](accesskey)
-   The [accesskey](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/accesskey) global attribute.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/accessKeyLabel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/accessKeyLabel</a>
