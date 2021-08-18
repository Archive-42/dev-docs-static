StorageEvent
============

A `StorageEvent` is sent to a window when a storage area it has access to is changed within the context of another document.

Method overview
---------------

    void initStorageEvent(
      in DOMString type,
      in boolean canBubble,
      in boolean cancelable,
      in DOMString key,
      in DOMString oldValue,
      in DOMString newValue,
      in USVString url,
      in Storage storageArea
    );

Attributes
----------

<table><thead><tr class="header"><th>Attribute</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>key</code></td><td><a href="domstring"><code>DOMString</code></a></td><td>Represents the key changed. The <code>key</code> attribute is <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null"><code>null</code></a> when the change is caused by the storage <code>clear()</code> method. <strong>Read only.</strong></td></tr><tr class="even"><td><code>newValue</code></td><td><a href="domstring"><code>DOMString</code></a></td><td>The new value of the <code>key</code>. The <code>newValue</code> is <code>null</code> when the change has been invoked by storage <code>clear()</code> method or the <code>key</code> has been removed from the storage. <strong>Read only.</strong></td></tr><tr class="odd"><td><code>oldValue</code></td><td><a href="domstring"><code>DOMString</code></a></td><td>The original value of the <code>key</code>. The <code>oldValue</code> is <code>null</code> when the <code>key</code> has been newly added and therefore doesn't have any previous value. <strong>Read only.</strong></td></tr><tr class="even"><td><code>storageArea</code></td><td><a href="storage"><code>Storage</code></a></td><td>Represents the <code>Storage</code> object that was affected. <strong>Read only.</strong></td></tr><tr class="odd"><td><code>url</code></td><td><a href="usvstring"><code>USVString</code></a></td><td>The URL of the document whose <code>key</code> changed. <strong>Read only.</strong></td></tr></tbody></table>

Methods
-------

### initStorageEvent()

Initializes the event in a manner analogous to the similarly-named [`initEvent()`](event/initevent) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> method in the DOM Events interfaces.

#### Syntax

    storageEvent.initStorageEvent(type[, canBubble[, cancelable[, key[, oldValue[, newValue[, url[, storageArea]]]]]]])

##### Parameters

`typeArg`  
The name of the event.

 `canBubble` <span class="badge inline optional">Optional</span>   
A boolean indicating whether the event bubbles up through the DOM or not.

 `cancelable` <span class="badge inline optional">Optional</span>   
A boolean indicating whether the event is cancelable.

 `key` <span class="badge inline optional">Optional</span>   
The key whose value is changing as a result of this event.

 `oldValue` <span class="badge inline optional">Optional</span>   
The key's old value.

 `newValue` <span class="badge inline optional">Optional</span>   
The key's new value.

 `url` <span class="badge inline optional">Optional</span>   
The URL of the document initiating the change.

 `storageArea` <span class="badge inline optional">Optional</span>   
The [`Storage`](storage) object representing the storage area on which this event occurred.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Statuc</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webstorage.html#the-storageevent-interface">HTML Living Standard<br />
<span class="small">The definition of 'The <code>StorageEvent</code> interface' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`StorageEvent`

1

12

Yes

?

Yes

Yes

1

Yes

Yes

Yes

Yes

Yes

`StorageEvent`

17

≤79

Yes

?

Yes

6

≤37

Yes

Yes

Yes

6

Yes

`initStorageEvent`

Yes

12

Yes

?

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`key`

1

12

Yes

?

Yes

Yes

1

Yes

Yes

Yes

Yes

Yes

`newValue`

1

12

Yes

?

Yes

Yes

1

Yes

Yes

Yes

Yes

Yes

`oldValue`

1

12

Yes

?

Yes

Yes

1

Yes

Yes

Yes

Yes

Yes

`storageArea`

3

12

Yes

?

Yes

Yes

≤37

Yes

Yes

Yes

Yes

Yes

`url`

5

12

Yes

?

Yes

Yes

≤37

Yes

Yes

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StorageEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StorageEvent</a>
