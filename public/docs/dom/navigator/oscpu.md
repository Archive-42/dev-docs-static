# Navigator.oscpu

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `Navigator.oscpu` property returns a string that identifies the current operating system.

## Syntax

    oscpuInfo = navigator.oscpu

### Value

A [`DOMString`](../domstring) providing a string which identifies the operating system on which the browser is running.

<table><thead><tr class="header"><th>Operating system</th><th><code>oscpuInfo</code> string format</th></tr></thead><tbody><tr class="odd"><td>OS/2</td><td>OS/2 Warp x (either 3, 4 or 4.5)</td></tr><tr class="even"><td>Windows CE</td><td>WindowsCE x.y<sup>1</sup></td></tr><tr class="odd"><td>Windows 64-bit (64-bit build)</td><td>Windows NT x.y; Win64; x64</td></tr><tr class="even"><td>Windows 64-bit (32-bit build)</td><td>Windows NT x.y; WOW64</td></tr><tr class="odd"><td>Windows 32-bit</td><td>Windows NT x.y</td></tr><tr class="even"><td>Mac OS X (PPC build)</td><td>PowerPC Mac OS X version x.y</td></tr><tr class="odd"><td>Mac OS X (i386/x64 build)</td><td>Intel Mac OS X or macOS version x.y</td></tr><tr class="even"><td>Linux 64-bit (32-bit build)</td><td>Output of <code>uname -s</code> plus <code>i686 on x86_64</code></td></tr><tr class="odd"><td>Linux</td><td>Output of <code>uname -sm</code></td></tr></tbody></table>

1.  x.y refers to the version of the operating system

## Example

    function osInfo() {
      alert(window.navigator.oscpu);
    }

    osInfo(); // alerts "Windows NT 6.0" for example

## Usage notes

Unless your code is privileged (chrome or at least has the UniversalBrowserRead privilege), it may get the value of the `general.oscpu.override` preference instead of the true platform.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-navigator-oscpu">HTML Living Standard<br />
<span class="small">The definition of 'NavigatorID: oscpu' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`oscpu`

No

No

1

The preference `"general.oscpu.override"` can be used to set a value to be returned instead of the true CPU description. The preference setting is ignored for calls made by privileged code, which continue to get the actual CPU description.

No

No

No

No

No

4

The preference `"general.oscpu.override"` can be used to set a value to be returned instead of the true CPU description. The preference setting is ignored for calls made by privileged code, which continue to get the actual CPU description.

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/oscpu" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/oscpu</a>
