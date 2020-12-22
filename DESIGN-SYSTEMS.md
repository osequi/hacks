# Design Systems

## Sanity.io

### Summary

- It's not fully finished. Contains just a few 'primitives' compared to MUI.
- Theory is not well thought.
- Technicaly perhaps brilliant.
- Docs are perfect.
- APi is clear.

### Findings

- https://www.sanity.io/ui
- https://github.com/sanity-io/design/tree/next/ui/src/components/menu
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

