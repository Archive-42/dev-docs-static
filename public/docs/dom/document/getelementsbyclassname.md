# Document.getElementsByClassName()

The `getElementsByClassName` method of [`Document`](../document) interface returns an array-like object of all child elements which have all of the given class name(s). When called on the [`document`](../document) object, the complete document is searched, including the root node. You may also call [`getElementsByClassName()`](../element/getelementsbyclassname) on any element; it will return only elements which are descendants of the specified root element with the given class name(s).

Warning: This is a live [`HTMLCollection`](../htmlcollection). Changes in the DOM will reflect in the array as the changes occur. If an element selected by this array no longer qualifies for the selector, it will automatically be removed. Be aware of this for iteration purposes.

## Syntax

    var elements = document.getElementsByClassName(names); // or:
    var elements = rootElement.getElementsByClassName(names);

- elements is a live [`HTMLCollection`](../htmlcollection) of found elements.
- names is a string representing the class name(s) to match; multiple class names are separated by whitespace
- [`getElementsByClassName`](../element/getelementsbyclassname) can be called on any element, not only on the [`document`](../document). The element on which it is called will be used as the root of the search.

## Examples

Get all elements that have a class of 'test':

    document.getElementsByClassName('test')

Get all elements that have both the 'red' and 'test' classes:

    document.getElementsByClassName('red test')

Get all elements that have a class of 'test', inside of an element that has the ID of 'main':

    document.getElementById('main').getElementsByClassName('test')

Get the first element with a class of 'test', or `undefined` if there is no matching element:

    document.getElementsByClassName('test')[0]

We can also use methods of Array.prototype on any [`HTMLCollection`](../htmlcollection) by passing the `HTMLCollection` as the method's this value. Here we'll find all div elements that have a class of 'test':

    var testElements = document.getElementsByClassName('test');
    var testDivs = Array.prototype.filter.call(testElements, function(testElement){
      return testElement.nodeName === 'DIV';
    });

### Get the first element whose class is 'test'

This is the most commonly used method of operation.

    <html>
    <body>
        <div id="parent-id">
            <p>hello world 1</p>
            <p class="test">hello world 2</p>
            <p>hello world 3</p>
            <p>hello world 4</p>
        </div>

        <script>
            var parentDOM = document.getElementById("parent-id");

            var test = parentDOM.getElementsByClassName("test"); // a list of matching elements, *not* the element itself
            console.log(test); //HTMLCollection[1]

            var testTarget = parentDOM.getElementsByClassName("test")[0]; // the first element, as we wanted
            console.log(testTarget); //<p class="test">hello world 2</p>
        </script>
    </body>
    </html>

### Multiple Classes Example

`document.getElementsByClassName` works very similarly to `document.querySelector` and `document.querySelectorAll`. Only elements with ALL of the classNames specified are selected.

#### HTML

    <span class="orange fruit">Orange Fruit</span>
    <span class="orange juice">Orange Juice</span>
    <span class="apple juice">Apple Juice</span>
    <span class="foo bar">Something Random</span>
    <textarea id="resultArea" style="width:98%;height:7em"></textarea>

#### JavaScript

    // getElementsByClassName only selects elements that have both given classes
    var allOrangeJuiceByClass = document.getElementsByClassName('orange juice');
    var result = "document.getElementsByClassName('orange juice')";
    for (var i=0, len=allOrangeJuiceByClass.length|0; i<len; i=i+1|0) {
        result += "\n  " + allOrangeJuiceByClass[i].textContent;
    }

    // querySelector only selects full complete matches
    var allOrangeJuiceQuery = document.querySelectorAll('.orange.juice');
    result += "\n\ndocument.querySelectorAll('.orange.juice')";
    for (var i=0, len=allOrangeJuiceQuery.length|0; i<len; i=i+1|0) {
        result += "\n  " + allOrangeJuiceQuery[i].textContent;
    }

    document.getElementById("resultArea").value = result;

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-getelementsbyclassname">DOM<br />
<span class="small">The definition of 'document.getElementsByClassName' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`getElementsByClassName`

1

12

3

9

9.5

3.1

1

18

4

10.1

2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName</a>
