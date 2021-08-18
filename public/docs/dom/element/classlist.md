Element.classList
=================

The `Element.classList` is a read-only property that returns a live [`DOMTokenList`](../domtokenlist) collection of the `class` attributes of the element. This can then be used to manipulate the class list.

Using `classList` is a convenient alternative to accessing an element's list of classes as a space-delimited string via [`element.className`](classname).

Syntax
------

    const elementClasses = elementNodeReference.classList;

### Returns

A [`DOMTokenList`](../domtokenlist) representing the contents of the element's `class` attribute. If the `class` attribute is not set or empty, it returns an empty `DOMTokenList`, i.e. a `DOMTokenList` with the `length` property equal to `0`.

The `DOMTokenList` itself is read-only, although you can modify it using the [`add()`](../domtokenlist/add) and [`remove()`](../domtokenlist/remove) methods.

Examples
--------

    const div = document.createElement('div');
    div.className = 'foo';

    // our starting state: <div class="foo"></div>
    console.log(div.outerHTML);

    // use the classList API to remove and add classes
    div.classList.remove("foo");
    div.classList.add("anotherclass");

    // <div class="anotherclass"></div>
    console.log(div.outerHTML);

    // if visible is set remove it, otherwise add it
    div.classList.toggle("visible");

    // add/remove visible, depending on test conditional, i less than 10
    div.classList.toggle("visible", i < 10 );

    console.log(div.classList.contains("foo"));

    // add or remove multiple classes
    div.classList.add("foo", "bar", "baz");
    div.classList.remove("foo", "bar", "baz");

    // add or remove multiple classes using spread syntax
    const cls = ["foo", "bar"];
    div.classList.add(...cls);
    div.classList.remove(...cls);

    // replace class "foo" with class "bar"
    div.classList.replace("foo", "bar");

Versions of Firefox before 26 do not implement the use of several arguments in the add/remove/toggle methods. See <https://bugzilla.mozilla.org/show_bug.cgi?id=814014>

Polyfill
--------

The legacy `onpropertychange` event can be used to create a living `classList` mockup thanks to a `Element.prototype.className` property that fires the specified event once it is changed.

The following polyfill for both `classList` and `DOMTokenList` ensures **full** compliance (coverage) for all standard methods and properties of `Element.prototype.classList` for **IE10**-**IE11** browsers plus *nearly* compliant behavior for **IE 6-9**. Check it out:

    // 1. String.prototype.trim polyfill
    if (!"".trim) String.prototype.trim = function(){ return this.replace(/^[\s]+|[\s]+$/g, ''); };
    (function(window){"use strict"; // prevent global namespace pollution
    if(!window.DOMException) (DOMException = function(reason){this.message = reason}).prototype = new Error;
    var wsRE = /[\11\12\14\15\40]/, wsIndex = 0, checkIfValidClassListEntry = function(O, V) {
      if (V === "") throw new DOMException(
        "Failed to execute '" + O + "' on 'DOMTokenList': The token provided must not be empty." );
      if((wsIndex=V.search(wsRE))!==-1) throw new DOMException("Failed to execute '"+O+"' on 'DOMTokenList': " +
        "The token provided ('"+V[wsIndex]+"') contains HTML space characters, which are not valid in tokens.");
    }
    // 2. Implement the barebones DOMTokenList livelyness polyfill
    if (typeof DOMTokenList !== "function") (function(window){
        var document = window.document, Object = window.Object, hasOwnProp = Object.prototype.hasOwnProperty;
        var defineProperty = Object.defineProperty, allowTokenListConstruction = 0, skipPropChange = 0;
        function DOMTokenList(){
            if (!allowTokenListConstruction) throw TypeError("Illegal constructor"); // internally let it through
        }
        DOMTokenList.prototype.toString = DOMTokenList.prototype.toLocaleString = function(){return this.value};
        DOMTokenList.prototype.add = function(){
            a: for(var v=0, argLen=arguments.length,val="",ele=this[" uCL"],proto=ele[" uCLp"]; v!==argLen; ++v) {
                val = arguments[v] + "", checkIfValidClassListEntry("add", val);
                for (var i=0, Len=proto.length, resStr=val; i !== Len; ++i)
                    if (this[i] === val) continue a; else resStr += " " + this[i];
                this[Len] = val, proto.length += 1, proto.value = resStr;
            }
            skipPropChange = 1, ele.className = proto.value, skipPropChange = 0;
        };
        DOMTokenList.prototype.remove = function(){
            for (var v=0, argLen=arguments.length,val="",ele=this[" uCL"],proto=ele[" uCLp"]; v !== argLen; ++v) {
                val = arguments[v] + "", checkIfValidClassListEntry("remove", val);
                for (var i=0, Len=proto.length, resStr="", is=0; i !== Len; ++i)
                    if(is){ this[i-1]=this[i] }else{ if(this[i] !== val){ resStr+=this[i]+" "; }else{ is=1; } }
                if (!is) continue;
                delete this[Len], proto.length -= 1, proto.value = resStr;
            }
            skipPropChange = 1, ele.className = proto.value, skipPropChange = 0;
        };
        window.DOMTokenList = DOMTokenList;
        function whenPropChanges(){
            var evt = window.event, prop = evt.propertyName;
            if ( !skipPropChange && (prop==="className" || (prop==="classList" && !defineProperty)) ) {
                var target = evt.srcElement, protoObjProto = target[" uCLp"], strval = "" + target[prop];
                var tokens=strval.trim().split(wsRE), resTokenList=target[prop==="classList"?" uCL":"classList"];
                var oldLen = protoObjProto.length;
                a: for(var cI = 0, cLen = protoObjProto.length = tokens.length, sub = 0; cI !== cLen; ++cI){
                    for(var innerI=0; innerI!==cI; ++innerI) if(tokens[innerI]===tokens[cI]) {sub++; continue a;}
                    resTokenList[cI-sub] = tokens[cI];
                }
                for (var i=cLen-sub; i < oldLen; ++i) delete resTokenList[i]; //remove trailing indexes
                if(prop !== "classList") return;
                skipPropChange = 1, target.classList = resTokenList, target.className = strval;
                skipPropChange = 0, resTokenList.length = tokens.length - sub;
            }
        }
        function polyfillClassList(ele){
            if (!ele || !("innerHTML" in ele)) throw TypeError("Illegal invocation");
            ele.detachEvent( "onpropertychange", whenPropChanges ); // prevent duplicate handler infinite loop
            allowTokenListConstruction = 1;
            try{ function protoObj(){} protoObj.prototype = new DOMTokenList(); }
            finally { allowTokenListConstruction = 0 }
            var protoObjProto = protoObj.prototype, resTokenList = new protoObj();
            a: for(var toks=ele.className.trim().split(wsRE), cI=0, cLen=toks.length, sub=0; cI !== cLen; ++cI){
                for (var innerI=0; innerI !== cI; ++innerI) if (toks[innerI] === toks[cI]) { sub++; continue a; }
                this[cI-sub] = toks[cI];
            }
            protoObjProto.length = cLen-sub, protoObjProto.value = ele.className, protoObjProto[" uCL"] = ele;
            if (defineProperty) { defineProperty(ele, "classList", { // IE8 & IE9 allow defineProperty on the DOM
                enumerable:   1, get: function(){return resTokenList},
                configurable: 0, set: function(newVal){
                    skipPropChange = 1, ele.className = protoObjProto.value = (newVal += ""), skipPropChange = 0;
                    var toks = newVal.trim().split(wsRE), oldLen = protoObjProto.length;
                    a: for(var cI = 0, cLen = protoObjProto.length = toks.length, sub = 0; cI !== cLen; ++cI){
                        for(var innerI=0; innerI!==cI; ++innerI) if(toks[innerI]===toks[cI]) {sub++; continue a;}
                        resTokenList[cI-sub] = toks[cI];
                    }
                    for (var i=cLen-sub; i < oldLen; ++i) delete resTokenList[i]; //remove trailing indexes
                }
            }); defineProperty(ele, " uCLp", { // for accessing the hidden prototype
                enumerable: 0, configurable: 0, writeable: 0, value: protoObj.prototype
            }); defineProperty(protoObjProto, " uCL", {
                enumerable: 0, configurable: 0, writeable: 0, value: ele
            }); } else { ele.classList=resTokenList, ele[" uCL"]=resTokenList, ele[" uCLp"]=protoObj.prototype; }
            ele.attachEvent( "onpropertychange", whenPropChanges );
        }
        try { // Much faster & cleaner version for IE8 & IE9:
            // Should work in IE8 because Element.prototype instanceof Node is true according to the specs
            window.Object.defineProperty(window.Element.prototype, "classList", {
                enumerable: 1,   get: function(val){
                                     if (!hasOwnProp.call(this, "classList")) polyfillClassList(this);
                                     return this.classList;
                                 },
                configurable: 0, set: function(val){this.className = val}
            });
        } catch(e) { // Less performant fallback for older browsers (IE 6-8):
            window[" uCL"] = polyfillClassList;
            // the below code ensures polyfillClassList is applied to all current and future elements in the doc.
            document.documentElement.firstChild.appendChild(document.createElement('style')).styleSheet.cssText=(
                '_*{x-uCLp:expression(!this.hasOwnProperty("classList")&&window[" uCL"](this))}' + //  IE6
                '[class]{x-uCLp/**/:expression(!this.hasOwnProperty("classList")&&window[" uCL"](this))}' //IE7-8
            );
        }
    })(window);
    // 3. Patch in unsupported methods in DOMTokenList
    (function(DOMTokenListProto, testClass){
        if (!DOMTokenListProto.item) DOMTokenListProto.item = function(i){
            function NullCheck(n) {return n===void 0 ? null : n} return NullCheck(this[i]);
        };
        if (!DOMTokenListProto.toggle || testClass.toggle("a",0)!==false) DOMTokenListProto.toggle=function(val){
            if (arguments.length > 1) return (this[arguments[1] ? "add" : "remove"](val), !!arguments[1]);
            var oldValue = this.value;
            return (this.remove(oldValue), oldValue === this.value && (this.add(val), true) /*|| false*/);
        };
        if (!DOMTokenListProto.replace || typeof testClass.replace("a", "b") !== "boolean")
            DOMTokenListProto.replace = function(oldToken, newToken){
                checkIfValidClassListEntry("replace", oldToken), checkIfValidClassListEntry("replace", newToken);
                var oldValue = this.value;
                return (this.remove(oldToken), this.value !== oldValue && (this.add(newToken), true));
            };
        if (!DOMTokenListProto.contains) DOMTokenListProto.contains = function(value){
            for (var i=0,Len=this.length; i !== Len; ++i) if (this[i] === value) return true;
            return false;
        };
        if (!DOMTokenListProto.forEach) DOMTokenListProto.forEach = function(f){
            if (arguments.length === 1) for (var i = 0, Len = this.length; i !== Len; ++i) f( this[i], i, this);
            else for (var i=0,Len=this.length,tArg=arguments[1]; i !== Len; ++i) f.call(tArg, this[i], i, this);
        };
        if (!DOMTokenListProto.entries) DOMTokenListProto.entries = function(){
            var nextIndex = 0, that = this;
            return {next: function() {
                return nextIndex<that.length ? {value: [nextIndex, that[nextIndex++]], done: false} : {done: true};
            }};
        };
        if (!DOMTokenListProto.values) DOMTokenListProto.values = function(){
            var nextIndex = 0, that = this;
            return {next: function() {
                return nextIndex<that.length ? {value: that[nextIndex++], done: false} : {done: true};
            }};
        };
        if (!DOMTokenListProto.keys) DOMTokenListProto.keys = function(){
            var nextIndex = 0, that = this;
            return {next: function() {
                return nextIndex<that.length ? {value: nextIndex++, done: false} : {done: true};
            }};
        };
    })(window.DOMTokenList.prototype, window.document.createElement("div").classList);
    })(window);

### Caveats

The polyfill is limited in functionality. It's currently unable to polyfill out-of-document-elements (e.g. elements created by `document.createElement` before they are appended to a parent node) in IE6-7.

However, it should work just fine in IE9. A major discrepancy between the polyfilled version of `classList` and the W3 specs is that for IE6-8, there is no way to create an immutable object (an object whose properties cannot be directly modified). In IE9, however, it is possible through extending the prototype, freezing the visible object, and overwriting native property methods. However, such actions would not work in IE6-IE8 and, in IE9, slow the performance of the entire webpage to a snail's crawl, making these modifications completely impractical for this polyfill.

A minor note is that in IE6-7, this polyfill uses the `window[" uCL"]` property on the window object for communicating with the CSS expressions, the `x-uCLp` css property on all elements, and the `element[" uCL"]` property on all elements to allow garbage collection and boost performance. In all polyfilled browsers (IE6-9), an additional `element[" uCLp"]` property is added to element to ensure standards compliant prototyping, and a `DOMTokenList[" uCL"]` property is added to each `element["classList"]` object to ensure that the DOMTokenList is bounded to its own element.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-classlist">DOM<br />
<span class="small">The definition of 'Element.classList' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/dom/#dom-element-classlist">DOM4<br />
<span class="small">The definition of 'Element.classList' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr></tbody></table>

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

`classList`

22

8-22

Not supported for SVG elements.

16

12-16

Not supported for SVG elements.

3.6

10

Not supported for SVG elements.

11.5

6.1

6-6.1

Not supported for SVG elements.

4.4

3-4.4

Not supported for SVG elements.

25

18-25

Not supported for SVG elements.

4

11.5

7

5-7

Not supported for SVG elements.

1.5

1.0-1.5

Not supported for SVG elements.

`add_and_remove_multiple_arguments`

24

12

26

No

15

7

≤37

25

26

14

7

1.5

`replace`

61

17

49

No

?

No

61

61

49

?

No

8.0

`toggle_method_second_argument`

24

12

24

No

15

7

≤37

Yes

24

?

7

Yes

See also
--------

-   [`element.className`](classname)
-   [`DOMTokenList`](../domtokenlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/classList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/classList</a>
