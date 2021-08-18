# ChildNode.after()

The `ChildNode.after()` method inserts a set of [`Node`](../node) or [`DOMString`](../domstring) objects in the children list of this `ChildNode`'s parent, just after this `ChildNode`. [`DOMString`](../domstring) objects are inserted as equivalent [`Text`](../text) nodes.

## Syntax

    [Throws, Unscopable]
    void ChildNode.after((Node or DOMString)... nodes);

### Parameters

`nodes`  
A set of [`Node`](../node) or [`DOMString`](../domstring) objects to insert.

### Exceptions

- <span class="page-not-created">`HierarchyRequestError`</span>: Node cannot be inserted at the specified point in the hierarchy.

## Examples

### Inserting an element

    var parent = document.createElement("div");
    var child = document.createElement("p");
    parent.appendChild(child);
    var span = document.createElement("span");

    child.after(span);

    console.log(parent.outerHTML);
    // "<div><p></p><span></span></div>"

### Inserting text

    var parent = document.createElement("div");
    var child = document.createElement("p");
    parent.appendChild(child);

    child.after("Text");

    console.log(parent.outerHTML);
    // "<div><p></p>Text</div>"

### Inserting an element and text

    var parent = document.createElement("div");
    var child = document.createElement("p");
    parent.appendChild(child);
    var span = document.createElement("span");

    child.after(span, "Text");

    console.log(parent.outerHTML);
    // "<div><p></p><span></span>Text</div>"

### `ChildNode.after()` is unscopable

The `after()` method is not scoped into the `with` statement. See [`Symbol.unscopables`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/unscopables) for more information.

    with(node) {
      after("foo");
    }
    // ReferenceError: after is not defined

## Polyfill

You can polyfill the `after()` method in Internet Explorer 9 and higher with the following code:

    // from: https://github.com/jserz/js_piece/blob/master/DOM/ChildNode/after()/after().md
    (function (arr) {
      arr.forEach(function (item) {
        if (item.hasOwnProperty('after')) {
          return;
        }
        Object.defineProperty(item, 'after', {
          configurable: true,
          enumerable: true,
          writable: true,
          value: function after() {
            var argArr = Array.prototype.slice.call(arguments),
              docFrag = document.createDocumentFragment();

            argArr.forEach(function (argItem) {
              var isNode = argItem instanceof Node;
              docFrag.appendChild(isNode ? argItem : document.createTextNode(String(argItem)));
            });

            this.parentNode.insertBefore(docFrag, this.nextSibling);
          }
        });
      });
    })([Element.prototype, CharacterData.prototype, DocumentType.prototype]);

### Another polyfill

    // from: https://github.com/FabioVergani/js-Polyfill_Element.prototype.after/blob/master/after.js

    (function(x){
     var o=x.prototype,p='after';
     if(!o[p]){
        o[p]=function(){
         var e, m=arguments, l=m.length, i=0, t=this, p=t.parentNode, n=Node, s=String, d=document;
         if(p!==null){
            while(i<l){
             e=m[i];
             if(e instanceof n){
                t=t.nextSibling;
                if(t!==null){
                    p.insertBefore(e,t);
                }else{
                    p.appendChild(e);
                };
             }else{
                p.appendChild(d.createTextNode(s(e)));
             };
             ++i;
            };
         };
        };
     };
    })(Element);

    /*
    minified:

    (function(x){
     var o=x.prototype;
     o.after||(o.after=function(){var e,m=arguments,l=m.length,i=0,t=this,p=t.parentNode,n=Node,s=String,d=document;if(p!==null){while(i<l){((e=m[i]) instanceof n)?(((t=t.nextSibling )!==null)?p.insertBefore(e,t):p.appendChild(e)):p.appendChild(d.createTextNode(s(e)));++i;}}});
    }(Element));
    */

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-childnode-after">DOM<br />
<span class="small">The definition of 'ChildNode.after()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`after`

54

17

49

No

39

10

54

54

49

41

10

6.0

## See also

- [`ChildNode.before()`](before)
- [`Element.append()`](../element/append)
- [`Node.appendChild()`](../node/appendchild)
- [`Element.insertAdjacentElement()`](../element/insertadjacentelement)
- [`NodeList`](../nodelist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/after" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/after</a>
