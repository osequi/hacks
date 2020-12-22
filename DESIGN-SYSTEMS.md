# Design Systems

An overview of a few Design Systems written in React.

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

