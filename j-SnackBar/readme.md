## j-SnackBar

- singleton
- info message `SETTER('snackbar', 'show', 'MESSAGE', '[BUTTON_LABEL]', [callback_dismiss])`
- success message `SETTER('snackbar', 'success', 'MESSAGE', '[BUTTON_LABEL]', [callback_dismiss])`
- warning message `SETTER('snackbar', 'warning', 'MESSAGE', '[BUTTON_LABEL]', [callback_dismiss])`
- __NEW__ waiting message `SETTER('snackbar', 'waiting', 'MESSAGE', '[BUTTON_LABEL]', [callback_dismiss])`
- `message` can contain `HTML` code

__Configuration__:

- `button` {String} A label for dismiss button (default: `OK`)
- `timeout` {Number} A timeout in milliseconds (default: `4000`)

__Works with ASETTER__:

- errors are handled automatically

```javascript
// Without callback
AJAX('POST /api/profile/', userprofile, ASETTER('snackbar', 'response', 'Profile has been saved successfully'));

// Or with a callback
AJAX('POST /api/profile/', userprofile, ASETTER('snackbar', 'response', 'Profile has been saved successfully', function(response) {
	console.log(response);
}));

// Or with a callback and without message
AJAX('POST /api/profile/', userprofile, ASETTER('snackbar', 'response', function(response) {
	console.log(response);
}));
````

### Author

- Peter Širka <petersirka@gmail.com>
- [License](https://www.totaljs.com/license/)