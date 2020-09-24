# Keys

- `shortid.generate()` inside a function component can generate an endless re-render loop.
- used outside, like in `props` works like a charm.
- see https://github.com/osequi/react-css-perspective/commit/41a09d39e19c9077a8fe9be8fac88db4e4d226eb
