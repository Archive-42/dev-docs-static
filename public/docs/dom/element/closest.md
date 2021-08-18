# Element.closest()

The `closest()` method traverses the [`Element`](../element) and its parents (heading toward the document root) until it finds a node that matches the provided selector string. Will return itself or the matching ancestor. If no such element exists, it returns `null`.

## Syntax

    var closestElement = targetElement.closest(selectors);

### Parameters

- `selectors` is a [`DOMString`](../domstring) containing a selector list.  
  ex: `p:hover, .toto + q`

### Return value

- `closestElement` is the [`Element`](../element) which is the closest ancestor of the selected element. It may be `null`.

### Exceptions

- [`SyntaxError`](../domexception#exception-syntaxerror) is thrown if the `selectors` is not a valid selector list string.

## Example

### HTML

    <article>
      <div id="div-01">Here is div-01
        <div id="div-02">Here is div-02
          <div id="div-03">Here is div-03</div>
        </div>
      </div>
    </article>

### JavaScript

    var el = document.getElementById('div-03');

    var r1 = el.closest("#div-02");
    // returns the element with the id=div-02

    var r2 = el.closest("div div");
    // returns the closest ancestor which is a div in div, here it is the div-03 itself

    var r3 = el.closest("article > div");
    // returns the closest ancestor which is a div and has a parent article, here it is the div-01

    var r4 = el.closest(":not(div)");
    // returns the closest ancestor which is not a div, here it is the outmost article

## Polyfill

For browsers that do not support `Element.closest()`, but carry support for `element.matches()` (or a prefixed equivalent, meaning IE9+), a polyfill exists:

    if (!Element.prototype.matches) {
      Element.prototype.matches =
        Element.prototype.msMatchesSelector ||
        Element.prototype.webkitMatchesSelector;
    }

    if (!Element.prototype.closest) {
      Element.prototype.closest = function(s) {
        var el = this;

        do {
          if (Element.prototype.matches.call(el, s)) return el;
          el = el.parentElement || el.parentNode;
        } while (el !== null && el.nodeType === 1);
        return null;
      };
    }

However, if you really do require IE 8 support, then the following polyfill will do the job very slowly, but eventually. However, it will only support CSS 2.1 selectors in IE 8, and it can cause severe lag spikes in production websites.

    if (window.Element && !Element.prototype.closest) {
      Element.prototype.closest = function(s) {
        var matches = (this.document || this.ownerDocument).querySelectorAll(s),
            i,
            el = this;
        do {
          i = matches.length;
          while (--i >= 0 && matches.item(i) !== el) {};
        } while ((i < 0) && (el = el.parentElement));
        return el;
      };
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-closest">DOM<br />
<span class="small">The definition of 'Element.closest()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`closest`

41

15

35

No

28

6

41

41

35

28

9

4.0

- In Edge 15-18 `document.createElement(tagName).closest(tagName)` will return `null` if the element is not first connected (directly or indirectly) to the context object, for example the [`Document`](../document) object in the case of the normal DOM.

## See also

- The [`Element`](../element) interface.
- [The syntax of Selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors)
- Other methods that take selectors: [`element.querySelector()`](queryselector) and [`element.matches()`](matches).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/closest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/closest</a>
