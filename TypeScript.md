# Typescript 

## Destructuring

- Hard to add types on destructuring: https://stackoverflow.com/questions/39672807/types-in-object-destructuring
- Workaround: instead of `const {fonts} = typography` :

```
const fonts = typography.fonts.reduce((result, item) => {
    return [...result, item];
  }, []);
```
