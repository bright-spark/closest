# closest

> Return the closest element matching a selector up the DOM tree

[![npm][npm-image]][npm-url] [![status][ci-img]][ci]
[![license][license-image]][license-url]
[![changelog][changelog-image]][changelog-url]
[![gitter][gitter-image]][gitter-url]

[closest] is a polyfill for [`#Element.closest`].

The [`#Element.closest`] method returns the closest ancestor of the current
element (or the current element itself) which matches the selectors given in
parameter. If there isn't such an ancestor, it returns null.

```js
element.closest(selectorString) //=> element
```

This is especially useful for delegating events.

```js
document.addEventListener('click', function (event) {
	// find nearest element up the tree that is an <a>
	var link = event.target.closest('a');

	if (link) {
		// do something with the <a>
		event.preventDefault();
	}
});
```

## matches

The  also polyfills [`#Element.matches`], which is
widely supported but often vendor-prefixed.

```js
element.matches(selectorString) //=> boolean
```

`matches` is especially useful for short-handing `hasAttribute` or
`classList.contains` with selectors.

```js
var widget = document.querySelector('.custom-widget');

if (widget.matches('[data-active]') || widget.matches('.widget--active')) {
	// do something with the active widget
}
```

## Browser compatibility

| Browser           | Native Support | Polyfill Support |
| ----------------- | -------------- | ---------------- |
| Android           | ✘              | 2.2+             |
| Blackberry        | ✘              | 7+               |
| Chrome            | 41+            | 4 - 40           |
| Edge              | ✘              | 12+              |
| Firefox           | 35+            | 3.5 - 34         |
| Internet Explorer | ✘              | 8+               |
| Opera             | 28+            | 10 - 27          |
| Opera Mini        | ✘              | 5+               |
| Safari (iOS)      | 9              | 3.2 - 8.4        |
| Safari (MacOS)    | 9.2+           | 3.1 - 8          |

### Internet Explorer 8

`closest` is especially useful for delegating events, but remember that
Internet Explorer 8 does not support [`#Element.addEventListener`].

[changelog-image]: https://img.shields.io/badge/changelog-md-blue.svg
[changelog-url]: CHANGELOG.md
[ci]: https://travis-ci.org/jonathantneal/closest
[ci-img]: https://img.shields.io/travis/jonathantneal/closest.svg
[gitter-image]: https://img.shields.io/badge/chat-gitter-blue.svg
[gitter-url]: https://gitter.im/jonathantneal/closest
[license-image]: https://img.shields.io/npm/l/element-closest.svg
[license-url]: LICENSE.md
[npm-image]: https://img.shields.io/npm/v/element-closest.svg
[npm-url]: https://www.npmjs.com/package/element-closest

[closest]: https://github.com/jonathantneal/closest
[`#Element.closest`]: https://dom.spec.whatwg.org/#dom-element-closest
[`#Element.matches`]: https://dom.spec.whatwg.org/#dom-element-matches
[`#Element.addEventListener`]: https://developer.mozilla.org/en-US/docs/Web/API/EventTarget.addEventListener#Browser_compatibility
