# Design Systems

An overview of a few Design Systems written in React.

## Material UI 

### Summary 

### Purpose

### Findings

### Takeaways - Where Somenage is worst

### Where Somenage is better



## Braid 

- https://seek-oss.github.io/braid-design-system/
- https://github.com/seek-oss/braid-design-system

### Summary 

- Almost as rich as MUI.
- Feels heavy.
- Almost everything except React is done in-house.

### Purpose

- For non-devs.
- Simplicity and composability of the API.

### Findings

- Typescript, with interfaces and types mixed up seeming randomly.
- Chaotic main folder structure, and also beyond.
- Themes and tokens are mixed up: https://github.com/seek-oss/braid-design-system/blob/master/lib/themes/seekUnifiedBeta/tokens.ts
- Uses an in-house styling system called `treat`
- In-house docs generator, in-house Storybook-like scenario testing
- No tests for components.

### Takeaways - Where Somenage is worst

- ?

### Where Somenage is better

- Lightweight
- Better theory

## Adobe Spectrum

- https://react-spectrum.adobe.com/index.html
- https://github.com/adobe/react-spectrum

### Summary 

- Almost as rich as MUI.
- Feels heavy.
- Not yet completed. There are no submenus, for example. React Aria lists cannot contain interactive elements like links, for example. 

### Purpose

- Accessible.
- To build Adobe apps.

### Findings

- Typescript with interfaces. It's more complicated than Sanity.
- Monorepo with Lerna and Yarn Workspaces
- Stylus
- Storybook for Spectrum, MDX for Aria.
- Class syntax
- Weak theory. Types are completely separated from code in a standalone package
- Well written unit tests
- Well structured code for every component: src, tests, docs, stories ...

### Takeaways - Where Somenage is worst

- Stately and Aria provide a very great foundation. One day Somenage might be built on it.
- Perhaps tests
- Everything seems well done, every part seems to be properly researched, but that makes it heavy, very heavy.

### Where Somenage is better

- Lighter

## Aragon UI

- https://ui.aragon.org/
- https://github.com/aragon/ui

### Summary

- Not as rich as MUI, but rich enough for simple UIs.
- No Typescript.
- Weak theory.
- No brilliant tech and code quality.

### Purpose

- Let devs build Aragon apps.

### Findings

- Nice UI
- Not as rich as MUI, but rich enough for simple UIs
- No Typescript
- Uses styled components
- Published to `npm`
- Complicated theme setup: https://github.com/aragon/ui/blob/master/src/theme/theme-dark.js
- Weak theory: stuff has to be st up in multiple folders.
- Weak theory: CSS is embedded in JSX
- No tests
- Nicely generated(?) READMEs.
- No live docs
- States in components well separated: https://github.com/aragon/ui/tree/master/src/components/Card

### Takeaways - Where Somenage is worst

- Docs UI, generated READMEs

### Where Somenage is better

- Better DX (better theory behind / better separation of concerns => easier to find stuff)
- Live API Docs (better comments)
- Better test coverage

## Sanity.io

- https://www.sanity.io/ui
- https://github.com/sanity-io/design

### Summary

- It's not fully finished. Contains just a few 'primitives' compared to MUI.
- Weak theory.
- Technicaly perhaps brilliant.
- Docs are perfect.
- API is clear.

### Purpose

- Have their own DS; don't rely on 3rd parties.
- Let devs compose UIs on their own.

### Findings

- Typescript with `interface`, looks pretty clean.
- Storybook vs. unit testing testing. Sometimes unit testing is present.
- Uses QA Wolf vs Cypress for e2e testing
- Uses Lerna, Yarn Workspaces; doesn't use module aliases.
- Styled components, css syntax
- Extensive use of Recat hooks, especially refs and callbacks
- Docs have a nice UI running on Next. Content comes from the Sanity backend, ie is not autogenereted.
- Concerns not separated: `Menu` component includes helpers, buttons, items etc. Maybe this is a 'single responisibility principle'.
- Concerns not separated: chaotic folder structure, can't figure out the logic. Couldn't found where to set up fonts.

### Takeaways - Where Somenage is worst

- Monorepo w Lerna
- Typescript
- API UI
- Very clean API. See the arcade.

### Where Somenage is better

- Better DX (better theory behind / better separation of concerns => easier to find stuff)
- Live API Docs (better comments)
- Better test coverage

