# HTMLOrForeignElement

**Draft**

This page is not complete.

The `HTMLOrForeignElement` mixin describes several features common to the [`HTMLElement`](htmlelement), [`SVGElement`](svgelement) and [`MathMLElement`](mathmlelement) interfaces. Each of these interfaces can, of course, add more features in addition to the ones listed below.

**Note**: `HTMLOrForeignElement` is a mixin and not an interface; you can't actually create an object of type `HTMLOrForeignElement`.

No compatibility data found for `api.HTMLOrForeignElement`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

[`dataset`](htmlorforeignelement/dataset) undefined  
The `dataset` read-only property of the `HTMLOrForeignElement` mixin provides read/write access to [custom data attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*) (`data-*`) on elements.

[`nonce`](htmlorforeignelement/nonce) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The `nonce` property of the `HTMLOrForeignElement` mixin returns the cryptographic number used once that is used by [Content Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) to determine whether a given fetch will be allowed to proceed.

[`tabIndex`](htmlorforeignelement/tabindex)  
The `tabIndex` property of the `HTMLOrForeignElement` mixin represents the tab order of the current element.

[`blur()`](htmlorforeignelement/blur)  
The `HTMLElement.blur()` method removes keyboard focus from the current element.

[`focus()`](htmlorforeignelement/focus)  
The `HTMLElement.focus()` method sets focus on the specified element, if it can be focused. The focused element is the element which will receive keyboard and similar events by default.

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/dom.html#htmlorsvgelement">HTML Living Standard<br />
<span class="small">The definition of '<code>HTMLOrForeignElement</code>' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

- [`HTMLElement`](htmlelement)
- [`SVGElement`](svgelement)
- [`MathMLElement`](mathmlelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement</a>
