# Hooks


## Can't render UI elements

They just return data, not parts of the UI.

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