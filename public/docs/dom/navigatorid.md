# NavigatorID

The `NavigatorID` interface contains methods and properties related to the identity of the browser.

There is no object of type `NavigatorID`, but other interfaces, like [`Navigator`](navigator) or [`WorkerNavigator`](workernavigator), implement it.

## Properties

_The `NavigatorID` interface doesn't inherit any properties._

[`NavigatorID.appCodeName`](navigatorid/appcodename) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Always returns "`Mozilla`", in any browser. This property is kept only for compatibility purposes.

[`NavigatorID.appName`](navigatorid/appname) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Always returns "`Netscape`", in any browser. This property is kept only for compatibility purposes.

[`NavigatorID.appVersion`](navigatorid/appversion) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns either "`4.0`" or a string representing version information about the browser. Do not rely on this property to return a useful value.

[`NavigatorID.platform`](navigatorid/platform) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns either the empty string or a string representing the platform the browser is running on. Do not rely on this property to return a useful value.

[`NavigatorID.product`](navigatorid/product) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Always returns "`Gecko`", in any browser. This property is kept only for compatibility purposes.

[`NavigatorID.userAgent`](navigatorid/useragent) <span class="badge inline readonly">Read only </span>  
Returns the user-agent string for the current browser.

## Methods

_The `NavigatorID` interface doesn't inherit any methods._

[`NavigatorID.taintEnabled()`](navigatorid/taintenabled) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Always returns `false`. JavaScript taint/untaint functions were removed in JavaScript 1.2. This method is only kept for compatibility purposes. Not available in workers.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#navigatorid">HTML Living Standard<br />
<span class="small">The definition of 'NavigatorID' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added the <code>appCodeName</code> property and the <code>taintEnabled()</code> method, for compatibility purpose.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/#navigatorid">HTML5<br />
<span class="small">The definition of 'NavigatorID' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`NavigatorID`

1

12

1

3

≤12.1

1

1

18

4

≤12.1

1

1.0

`appCodeName`

1

12

1

3

≤12.1

1

1

18

4

≤12.1

1

1.0

`appName`

1

12

1

3

≤12.1

1

1

18

4

≤12.1

1

1.0

`appVersion`

1

12

1

3

≤12.1

1

1

18

4

≤12.1

1

1.0

`platform`

1

12

1

\["Prior to Firefox 69, `platform` would report running on a 32-bit CPU if running the 32-bit version of Firefox on a 64-bit system.", "You can override the value returned by `platform` by setting the preference `general.platform.override` to the string you wish to be returned instead."\]

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`product`

1

12

1

11

15

1

1

18

4

14

1

1.0

`taintEnabled`

No

No

1

6

≤12.1-15

No

No

No

4

≤12.1-14

No

No

`userAgent`

1

12

1

3

≤12.1

1

1

18

4

≤12.1

1

1.0

## See also

- The [`Navigator`](navigator) and [`WorkerNavigator`](workernavigator) interfaces that implement it.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID</a>
