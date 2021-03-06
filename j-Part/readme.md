# j-Part

This component can handle different contents asynchronously. __If the element doesn't contain any content__ then the component downloads the content according to the `url` defined in configuration.

__Configuration__:

- `url` {String} required, a relative URL address
- `if` {String} required, condition, it's compared with the value within of `data-jc-path`
- `reload` {String} optional, a link to function `function(init) {}`, it's executed when the part is visible (always)
- `hidden` {String} optional, a link to function, it's executed when the part is hidden (always)
- `init` {String} optional, a link to function, it's executed when the part is visible and onetime
- `default` {String} optional, a short alias for `DEFAULT(default)`
- `hide` {Boolean} optional, auto-hide element if the `if` condition is not valid (default: `true`)
- `cleaner` {Number} optional, idle time (in minutes) for running of cleaning (default: `0`)
- `clean` {String} optional, a link to function, it's executed before the part is cleaned
- `loading` {Bollean} optional, enables loading via `SETTER('loading')` (default: `true`)
- __NEW__ `path` {String} optional, the component replace all `~PATH~` phrases for the value of the `path` in the downloaded template
- __NEW__ `replace` {String} optional, a link to method `function(content) { return content }` which can modify downloaded template
- __NEW__ `absolute` {Boolean} optional, enables absolute position (default `false`)

__Good to know__:

Part component emits an event in the form: `parts.` + `config.if` for extending of parts. This can be very usefull for some plugin systems. Example:

```javascript
ON('parts.pages', function(element, partcomponent) {
	// It's executed only when the part is initialized
});
```