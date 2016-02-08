# browser-platform

This is a naive implementation of browser/platform detection in JavaScript.

It is exported as a CommonJS/Node-style module, the main exports is a function that is meant to be called by passing in the useragent.

```
// CommonJS/Node Import
var platform = require('browser-platform')(window.navigator.userAgent)

// Direct browser injection
var platform = getBrowserPlatform(window.navigator.userAgent);
document.documentElement.setAttribute('class', ['js'].concat(platform.classNames).join(' '))
```

When run client-side some features (namely touch) are detected from the environment if not easily determined from the useragent. Android and iOS assume touch.

You can use `platform.classes.join(' ')` as CSS classes to be added to the `html` element, which can help with platform specific quirks.

The base portable detection portion of the script originated with [detectmobilebrowser.com](http://detectmobilebrowser.com/)'s regular expression(s).  The rest was written by [me](http://github.com/tracker1).  This library is released under a permissive [ISC](https://opensource.org/licenses/ISC) license.  It has been very useful for me, and at 2.3KB minified and gzipped, much smaller than most detection libraries. 
