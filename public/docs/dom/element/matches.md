# Element.matches()

The `matches()` method checks to see if the [`Element`](../element) would be selected by the provided `selectorString` -- in other words -- checks if the element "is" the selector.

## Syntax

    var result = element.matches(selectorString);

### Parameters

`selectorString` is a string representing the selector to test.

### Return value

`result` is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

### Exceptions

`SYNTAX_ERR`  
The specified selector string is invalid.

## Example

    <ul id="birds">
      <li>Orange-winged parrot</li>
      <li class="endangered">Philippine eagle</li>
      <li>Great white pelican</li>
    </ul>

    <script type="text/javascript">
      var birds = document.getElementsByTagName('li');

      for (var i = 0; i < birds.length; i++) {
        if (birds[i].matches('.endangered')) {
          console.log('The ' + birds[i].textContent + ' is endangered!');
        }
      }
    </script>

This will log "The Philippine eagle is endangered!" to the console, since the element has indeed a `class` attribute with value `endangered`.

## Polyfill

For browsers that do not support `Element.matches()` or `Element.matchesSelector()`, but include support for `document.querySelectorAll()`, a polyfill exists:

    if (!Element.prototype.matches) {
      Element.prototype.matches =
          Element.prototype.matchesSelector ||
          Element.prototype.mozMatchesSelector ||
          Element.prototype.msMatchesSelector ||
          Element.prototype.oMatchesSelector ||
          Element.prototype.webkitMatchesSelector ||
          function(s) {
            var matches = (this.document || this.ownerDocument).querySelectorAll(s),
                i = matches.length;
            while (--i >= 0 && matches.item(i) !== this) {}
            return i > -1;
          };
    }

However, given the practicality of supporting older browsers, the following should suffice for most (if not all) practical cases (i.e. IE9+ support).

    if (!Element.prototype.matches) {
      Element.prototype.matches = Element.prototype.msMatchesSelector ||
                                  Element.prototype.webkitMatchesSelector;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-matches">DOM<br />
<span class="small">The definition of 'Element.prototype.matches' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`matches`

33

4

15

12

12

34

44

3.6

\["Prior to Firefox 4, invalid selector strings caused false to be returned instead of throwing an exception.", "See [bug 1119718](https://bugzil.la/1119718) for removal."\]

9

21

15

11.5-15

7

5

4.4

≤37

33

18

34

44

4

See [bug 1119718](https://bugzil.la/1119718) for removal.

21

14

11.5-14

8

4.2

2.0

1.0

## See also

- [The syntax of Selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors)
- Other methods that take selectors: [`element.querySelector()`](queryselector) and [`element.closest()`](closest).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/matches" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/matches</a>
