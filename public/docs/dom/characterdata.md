# CharacterData

The `CharacterData` abstract interface represents a [`Node`](node) object that contains characters. This is an abstract interface, meaning there aren't any objects of type `CharacterData`: it is implemented by other interfaces like [`Text`](text), [`Comment`](comment), or [`ProcessingInstruction`](processinginstruction), which aren't abstract.

## Properties

_`CharacterData` inherits properties from its parent, [`Node`](node)._

[`CharacterData.data`](characterdata/data)  
Is a [`DOMString`](domstring) representing the textual data contained in this object.

[`CharacterData.length`](characterdata/length) <span class="badge inline readonly">Read only </span>  
Returns an `unsigned long` representing the size of the string contained in `CharacterData.data`.

[`Element.nextElementSibling`](element/nextelementsibling) <span class="badge inline readonly">Read only </span>  
Returns the [`Element`](element) immediately following the specified one in its parent's children list, or `null` if the specified element is the last one in the list.

[`Element.previousElementSibling`](element/previouselementsibling) <span class="badge inline readonly">Read only </span>  
Returns the [`Element`](element) immediately prior to the specified one in its parent's children list, or `null` if the specified element is the first one in the list.

## Methods

_`CharacterData` inherits methods from its parent, [`Node`](node)._

[`CharacterData.appendData()`](characterdata/appenddata)  
Appends the given [`DOMString`](domstring) to the `CharacterData.data` string; when this method returns, `data` contains the concatenated [`DOMString`](domstring).

[`CharacterData.deleteData()`](characterdata/deletedata)  
Removes the specified amount of characters, starting at the specified offset, from the `CharacterData.data` string; when this method returns, `data` contains the shortened [`DOMString`](domstring).

[`CharacterData.insertData()`](characterdata/insertdata)  
Inserts the specified characters, at the specified offset, in the `CharacterData.data` string; when this method returns, `data` contains the modified [`DOMString`](domstring).

[`ChildNode.remove()`](childnode/remove) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Removes the object from its parent children list.

[`CharacterData.replaceData()`](characterdata/replacedata)  
Replaces the specified amount of characters, starting at the specified offset, with the specified [`DOMString`](domstring); when this method returns, `data` contains the modified [`DOMString`](domstring).

[`CharacterData.substringData()`](characterdata/substringdata)  
Returns a [`DOMString`](domstring) containing the part of `CharacterData.data` of the specified length and starting at the specified offset.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#characterdata">DOM<br />
<span class="small">The definition of 'CharacterData' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added implementation of the <a href="childnode"><code>ChildNode</code></a> and <a href="element"><code>Element</code></a> interface.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-FF21A306">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'CharacterData' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Core/">Document Object Model (DOM) Level 2 Core Specification</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-FF21A306">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'CharacterData' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-FF21A306">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'CharacterData' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CharacterData`

1

12

1

5

≤12.1

1

1

18

Yes

≤12.1

1

1.0

`appendData`

1

12

Yes

6

≤12.1

1

1

18

Yes

≤12.1

1

1.0

`data`

1

12

Yes

5

≤12.1

1

1

18

Yes

≤12.1

1

1.0

`deleteData`

1

12

Yes

6

≤12.1

1

1

18

Yes

≤12.1

1

1.0

`insertData`

1

12

Yes

6

≤12.1

1

1

18

Yes

≤12.1

1

1.0

`length`

1

12

Yes

5

≤12.1

1

1

18

Yes

≤12.1

1

1.0

`nextElementSibling`

29

17

25

No

16

9

≤37

29

25

16

9

2.0

`previousElementSibling`

29

17

25

No

16

9

≤37

29

25

16

9

2.0

`replaceData`

1

12

Yes

6

≤12.1

1

1

18

Yes

≤12.1

1

1.0

`substringData`

1

12

Yes

6

≤12.1

1

1

18

Yes

≤12.1

1

1.0

## See also

- [The DOM interfaces index](document_object_model).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CharacterData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CharacterData</a>
