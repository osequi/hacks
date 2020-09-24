# Keys

## shortid

### Placement 

- `shortid.generate()` inside a function component can generate an endless re-render loop.
- used outside, like in `props` works like a charm.
- see https://github.com/osequi/react-css-perspective/commit/41a09d39e19c9077a8fe9be8fac88db4e4d226eb

### Reuse

- structures using a `shortid.generate()` can't be really reused.
- in the repo above we have two Control sets which differ only in title, the items are the same. when the second component tries to reuse the controls from the first component it fails, because that DOM node with taht shortid was already displyed.