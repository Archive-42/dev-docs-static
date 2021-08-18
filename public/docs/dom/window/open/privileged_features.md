Privileged features
===================

This page lists the `windowFeatures` parameter of [window.open](../open) function that requires chrome-privilege in Firefox.

This is not for web content.

The following features require the chrome-privilege.

`centerscreen`  
Centers the window in relation to its parent's size and position.

`minimizable`  
This setting can only apply to dialog windows; `minimizable` requires `dialog=yes`. If `minimizable` is on, the new dialog window will have a minimize system command icon in the titlebar and it will be minimizable. Any non-dialog window is always minimizable and `minimizable=no` will be ignored.

`dependent`  
If on, the new window is said to be dependent of its parent window. A dependent window closes when its parent window closes. A dependent window is minimized on the Windows task bar only when its parent window is minimized. On Windows platforms, a dependent window does not show on the task bar. A dependent window also stays in front of the parent window.

Dependent windows are not implemented on MacOS X, this option will be ignored.

The dependent feature is currently under revision to be removed ([bug 214867](https://bugzilla.mozilla.org/show_bug.cgi?id=214867))

In MSIE 6, the nearest equivalent to this feature is the `showModelessDialog()` method.

`chrome`  
If on, the page is loaded as window's only content, without any of the browser's interface elements. There will be no context menu defined by default and none of the standard keyboard shortcuts will work. The page is supposed to provide a user interface of its own, usually this feature is used to open XUL documents (standard dialogs like the JavaScript Console are opened this way).

`dialog`  
[<img src="data:image/png;base64,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" class="internal lwrap" width="170" height="170" />](menusystemcommands.png) The `dialog` feature removes all icons (restore, minimize, maximize) from the window's titlebar, leaving only the close button. Mozilla 1.2+ and Netscape 7.1 will render the other menu system commands (in FF 1.0 and in NS 7.0x, the command system menu is not identified with the Firefox/NS 7.0x icon on the left end of the titlebar: that's probably a bug. You can access the command system menu with a right-click on the titlebar). Dialog windows are windows which have no minimize system command icon and no maximize/restore down system command icon on the titlebar nor in correspondent menu item in the command system menu. They are said to be dialog because their normal, usual purpose is to only notify info and to be dismissed, closed. On Mac systems, dialog windows have a different window border and they may get turned into a sheet.

`modal`  
If on, the new window is said to be modal. The user cannot return to the main window until the modal window is closed. A typical modal window is created by the [alert() function](../alert).

The exact behavior of modal windows depends on the platform and on the Mozilla release version.

**Note:** As of Gecko 1.9, the Internet Explorer equivalent to this feature is the [`window.showModalDialog()`](../showmodaldialog) method. For compatibility reasons, it's now supported in Firefox. Note also that starting in Gecko 2.0, you can use [`window.showModalDialog()`](../showmodaldialog) without UniversalBrowserWrite privileges.

`titlebar`  
By default, all new secondary windows have a titlebar. If set to no or 0, this feature removes the titlebar from the new secondary window.

Mozilla and Firefox users can force new windows to always render the titlebar by setting  
`dom.disable_window_open_feature.titlebar`  
to true in [about:config](https://support.mozilla.com/en-US/kb/Editing+configuration+files#about_config) or in their [user.js file](https://support.mozilla.com/en-US/kb/Editing+configuration+files#user_js).

`alwaysRaised`  
If on, the new window will always be displayed on top of other browser windows, regardless of whether it is active or not.

`alwaysLowered`  
If on, the new created window floats below, under its own parent when the parent window is not minimized. alwaysLowered windows are often referred as pop-under windows. The alwaysLowered window can not be on top of the parent but the parent window can be minimized. In NS 6.x, the alwaysLowered window has no minimize system command icon and no restore/maximize system command.

`alwaysOnTop`  
If on, the new window will always be displayed on top of all other windows (browser windows and otherwise), regardless of whether it is active or not. This was added in Firefox 66 (see [bug 1519893](https://bugzilla.mozilla.org/show_bug.cgi?id=1519893)).

`z-lock`  
Same as `alwaysLowered`.

`close`  
When set to no or 0, this feature removes the system close command icon and system close menu item. It will only work for dialog windows (`dialog` feature set). `close=no` will override `minimizable=yes`.

Mozilla and Firefox users can force new windows to always have a close button by setting  
`dom.disable_window_open_feature.close`  
to true in [about:config](https://support.mozilla.com/en-US/kb/Editing+configuration+files#about_config) or in their [user.js file](https://support.mozilla.com/en-US/kb/Editing+configuration+files#user_js).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/open/Privileged_features" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/open/Privileged_features</a>
