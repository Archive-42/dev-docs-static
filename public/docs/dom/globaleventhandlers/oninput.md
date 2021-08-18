# GlobalEventHandlers.oninput

The `oninput` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `input` events on the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), and [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) elements. It also handles these events on elements where [`contenteditable`](../htmlelement/contenteditable) or [`designMode`](../document/designmode) are turned on.

**Note:** Unlike `oninput`, the [`onchange`](onchange) event handler is not necessarily called for each alteration to an element's `value`.

## Syntax

    target.oninput = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives an [`InputEvent`](../inputevent) object as its sole argument.

## Example

This example logs the number of characters in an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element, every time you modify its contents.

### HTML

    <input type="text" placeholder="Type something here to see its length." size="50">
    <p id="log"></p>

### JavaScript

    let input = document.querySelector('input');
    let log = document.getElementById('log');

    input.oninput = handleInput;

    function handleInput(e) {
      log.textContent = `The field's value is
          ${e.target.value.length} character(s) long.`;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#ix-handler-oninput">HTML Living Standard<br />
<span class="small">The definition of 'oninput' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`oninput`

1

12

9

9

10

4

1

18

9

10.1

3.2

1.0

The following links discuss compatibility issues and fixes that may be helpful when working with older browsers:

- [A HTML5 Browser maze, oninput support](https://blog.danielfriesen.name/2010/02/16/html5-browser-maze-oninput-support/)
- [Fixing oninput in IE Using html5Widgets](https://www.useragentman.com/blog/2011/05/12/fixing-oninput-in-ie9-using-html5widgets/) includes polyfill for IE6-8
- Mathias Bynens suggests [binding to both input and keydown](https://mathiasbynens.be/notes/oninput)
- [oninput event | dottoro](http://help.dottoro.com/ljhxklln.php) has notes about bugginess in IE9
- [Bug 312094 - Add support for &lt;select oninput&gt;](https://bugzilla.mozilla.org/show_bug.cgi?id=312094)

## See also

- `input` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oninput" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oninput</a>
