# detector-of-inspector
detect inspector opened in current tab of browser


```javascript
var detectOpened = function(){
			var elem = new Image();
			Object.defineProperty(elem, 'id', {
				get : function(){
					/* Do your Stuff Here */
					document.body.style.background = 'tomato';
					document.querySelector('h1').innerHTML = "Aha Caught'ya!'<br>Inspector Opened";
					detectClosed();
				}
			});
			console.log("Hello", elem);
		};
```

```javascript
var detectClosed = function(){
			var elem = new Image();
			var timeout = null;
			Object.defineProperty(elem, 'id', {
				get: function(){
					clearTimeout(timeout);
					timeout = setTimeout(function(){
						document.body.style.background = 'teal';
						document.querySelector('h1').innerHTML = 'Dare you open Inspector on this Tab(Ctrl+Shift+i)';
						console.clear();
						detectOpened();
					}, 1100);
					setTimeout(function(){console.log(elem)}, 1000);
				}
			});
```
