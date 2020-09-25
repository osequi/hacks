# Hooks

## Can render UI elements when packaged with Bit.dev

- See example at: https://github.com/osequi/react-css-perspective/blob/master/src/components/SquareMove/SquareMove.js

## Can't render UI elements when packaged as `npm`

- They just return data, cannot return parts of the UI.
- This might be a peer dependencies problem:
  - https://stackoverflow.com/questions/63892194/react-16-hooks-dont-work-in-nested-npm-package
  - https://developpaper.com/understanding-peer-dependencies/

### Examples

```js
return (
  <Control
    {...item}
    key={id}
    value={values[camelCase(label)]}
    eventHandler={eventHandler}
  />
);
```

Gives the following error:

```
Failed to compile

./node_modules/@osequi/use-controls/useControls.js
SyntaxError: /home/cs/osequi/use-controls/demo/node_modules/@osequi/use-controls/useControls.js: Unexpected token (65:8)

  63 |
  64 |       return (
> 65 |         <Control
     |         ^
  66 |           {...item}
  67 |           key={id}
  68 |           value={values[camelCase(label)]}
```

In the same way in `use-markdown` the `html` return value had to be removed. Now the hook returns only `markdown`.

```js
// Previously ...

const useMarkdown = (file) => {
  const [markdown, setMarkdown] = useState("");

  useEffect(() => {
    fetch(file)
      .then((response) => {
        return response.text();
      })
      .then((text) => {
        setMarkdown(marked(text));
      });
  }, [file]);

  const html = <div dangerouslySetInnerHTML={{ __html: markdown }} />;

  return { markdown: markdown, html: html };
};
```

The `<div>` gave the same `Unexpected token` error message.

```js
// Now ...
const [markdown, setMarkdown] = useState("");

useEffect(() => {
  fetch(file)
    .then((response) => {
      return response.text();
    })
    .then((text) => {
      setMarkdown(marked(text));
    });
}, [file]);

return { markdown: markdown };
```
