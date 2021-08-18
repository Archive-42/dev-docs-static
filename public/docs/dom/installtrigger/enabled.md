# InstallTrigger.enabled

## Summary

Indicates whether or not Software Installation is enabled for this client machine.

## Method of

[InstallTrigger](../installtrigger) object

## Syntax

    Boolean enabled ();

### Parameters

None

### Returns

True if Software Installation is enabled for this client machine; otherwise, false. The method reflects the value of the Software Installation preference in the user interface, and of the `xpinstall.enabled `preference in pref.js.

## Example

The following code uses the [startSoftwareUpdate](startsoftwareupdate) method to unconditionally trigger a download from `http://royalairways/royalpkg.xpi` as long as Software Installation is enabled on the browser:

    if (InstallTrigger.enabled() ) {
        InstallTrigger.startSoftwareUpdate ("http://royalair.com/rasoft.xpi");
    }

<a href="https://developer.mozilla.org/en-US/docs/Web/API/InstallTrigger/enabled" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/InstallTrigger/enabled</a>
