Obsolete features
=================

This page lists the obsolete `windowFeatures` parameter of [window.open](../open) function.

 `directories` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Obsolete synonym of personalbar. In IE, it rendered the Links bar. Supported in Gecko up to 1.9.2 and in IE up to 6.

`fullscreen`  
This feature no longer works in MSIE 6 SP2 the way it worked in MSIE 5.x. The Windows taskbar, as well as the titlebar and the status bar of the window are not visible, nor accessible when fullscreen is enabled in MSIE 5.x.  
`fullscreen` always upsets users with large monitor screen or with dual monitor screen. Forcing `fullscreen` onto other users is also extremely unpopular and is considered an outright rude attempt to impose web author's viewing preferences onto users.  
`fullscreen` does not really work in MSIE 6 SP2.

 `personalbar` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
If this feature is on, then the new secondary window renders the Personal Toolbar in Netscape 6.x, Netscape 7.x and Mozilla browser. It renders the Bookmarks Toolbar in Firefox. In addition to the Personal Toolbar, Mozilla browser will render the Site Navigation Bar if such toolbar is visible, present in the parent window.  
Mozilla and Firefox users can force new windows to always render the Personal Toolbar/Bookmarks toolbar by setting `dom.disable_window_open_feature.personalbar` to true in [about:config](https://support.mozilla.com/en-US/kb/Editing+configuration+files#about_config) or in their [user.js file](https://support.mozilla.com/en-US/kb/Editing+configuration+files#user_js).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/open/Obsolete_features" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/open/Obsolete_features</a>
