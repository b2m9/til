# Keypress, keydown, and keyup

Key codes in Javascript are not consistent among events `keypress`, `keydown`, and `keyup`.

`keydown` and `keyup` always return key codes for upper case letters, while `keypress` differentiates between cases but returns lower case by default.

Special keys like backspace, arrow keys, etc. are not captured by `keypress`. One has to use `keydown` or `keyup` for such cases.

For inconsistencies across browsers, see Quirksmode [1].

Website to test key codes: [www.asquare.net/javascript/tests/KeyCode.html](http://www.asquare.net/javascript/tests/KeyCode.html)

References:
- [1] [Quirksmode: Keys](http://www.quirksmode.org/js/keys.html)