disable-console.js

```javascript
// Reference http://davidwalsh.name/disable-console
// It appears Netflix is following (Facebook's lead)[https://news.ycombinator.com/item?id=7222129].

(function() {
    try {
        var $_console$$ = console;
        Object.defineProperty(window, "console", {
            get: function() {
                if ($_console$$._commandLineAPI)
                    throw "Sorry, for security reasons, the script console is deactivated on netflix.com";
                return $_console$$
            },
            set: function($val$$) {
                $_console$$ = $val$$
            }
        })
    } catch ($ignore$$) {
    }
})();
```