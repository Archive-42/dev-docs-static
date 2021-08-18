# Element.part

The `part` property of the [`Element`](../element) interface represents the part identifier(s) of the element (i.e. set using the `part` attribute), returned as a [`DOMTokenList`](../domtokenlist). These can be used to style parts of a shadow DOM, via the [`::part`](https://developer.mozilla.org/en-US/docs/Web/CSS/::part) pseudo-element.

## Syntax

    let elementPartList = element.part

## Examples

The following excerpt is from our [shadow-part](https://mdn.github.io/web-components-examples/shadow-part/) example. Here the `part` attribute is used to find the shadow parts, and the `part` property is then used to change the part identifiers of each tab so the correct styling is applied to the active tab when tabs are clicked.

    let tabs = [];
    let children = this.shadowRoot.children;

    for(let elem of children) {
      if(elem.getAttribute('part')) {
        tabs.push(elem);
      }
    }

    tabs.forEach((tab) => {
      tab.addEventListener('click', (e) => {
        tabs.forEach((tab) => {
          tab.part = 'tab';
        })
        e.target.part = 'tab active';
      })

      console.log(tab.part);
    })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-shadow-parts-1/#idl">Shadow Parts<br />
<span class="small">The definition of 'Element.part' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`part`

73

79

72

71

No

60

13.1

73

73

79

52

13.4

11.0

## See also

- [`::part`](https://developer.mozilla.org/en-US/docs/Web/CSS/::part)
- [`part`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-part)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/part" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/part</a>
