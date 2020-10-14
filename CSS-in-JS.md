# CSS in JS

- None of them is perfect
- The learning curve is high
- You can run in problems anytime with any of the libraries

A good overview: https://github.com/mui-org/material-ui/issues/22342
Speed of rendering: https://tuchk4.github.io/css-in-js-app

## Emotion

- Works out of the box: https://github.com/osequi/test-emotion
- It has a few, but all mandatory features, which all work fine.
- For example theming is missing, ie. is part of the `@emotion/core` which is not CRA compatible. But theming is not mandatory.
- MUI will move to Emotion
- Emotion is the fastest among the actively maintained major packages: JSS (MUI), Styled-components, Fela

## JSS

- Can't use props for keyframes: https://github.com/cssinjs/jss/issues/1216
- The same bug is present in MUI
- The `theme.custom` vs `props` hack works only once.

## Material UI

- So far the most complete solution for object notation
- Used at Lynx by many people and many projects and it simply goes straightforward

### `props` are not working inside `["& :not(:nth-child ...]` selectors

- `makeStyles()` is very strange. See the API at https://material-ui.com/styles/api/#makestyles-styles-options-hook
- To fix it `theme` is used. HOWEVER it turns out the hack works only once in a series of calls: https://github.com/osequi/somenage/commit/0beef63f6bf0249bb412716526b294c71f4c7278

Example:

```js
const useStyles = makeStyles((theme) => ({
  /**
   * Creates the faux lines CSS
   */
  fauxLines: {
    ["&  > *"]: {
      boxSizing: "border-box",

// This works
      [`${theme.custom.borderLeftSelector2}`]: {
        borderLeft: (props) => (props.displayHorizontal ? "1px solid" : "none"),
      },

// This ain't works at all
      [`&:not(:nth-child(${(props) => props.borderBottomException}))`]: {
        borderBottom: (props) => (props.displayVertical ? "1px solid" : "none"),
      },
    },
  },
  ...
```

However this works fine (`props.selector` is "> *") :

```js
container: (props) => ({
    display: "flex",
    justifyContent: "space-between",

    [`& ${props.selector}`]: {
      background: "red",
    },
  }),
```

## Styled components

- It's the de facto standard
- Yet neither `css` nor `styled` nor string literals nor object notation works perfectly.
- Some stuff can be solved only bby one of the above approaches. Some stuff with another.
- Combining them together is possible but many times is a nightmare
