# Design Systems

## Sanity.io

### Summary

- Theory is not well thought.
- Technicaly perhaps brilliant.

### Findings

- https://www.sanity.io/ui
- https://github.com/sanity-io/design/tree/next/ui/src/components/menu
- Typescript with `interface`, looks pretty clean.
- Storybook vs. unit testing testing. Sometimes unit testing is present.
- Uses QA Wolf vs Cypress for e2e testing
- Uses Lerna, Yarn Workspaces; doesn't use module aliases.
- Styled components, css syntax
- Extensive use of Recat hooks, especially refs and callbacks
- Concerns not separated: `Menu` component includes helpers, buttons, items etc. Maybe this is a 'single responisibility principle'.
- Concerns not separated: chaotic folder structure, can't figure out the logic. Couldn't found where to set up fonts.

### Where Somenage is worst (Takeaways)

- Monorepo w Lerna
- Typescript

### Where Somenage is better (Unique Selling Points)

- Easier to use (better theory behind)
- Live API Docs (better comments)
- Better test coverage

