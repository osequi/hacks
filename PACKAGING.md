# Packaging

## Bit.dev

- `bit import` gives `Error: Invalid hook call.` on usage.
- So the way to modify a package is: 1. copy to the current project 2. edit 3. copy back to the home dir 4. publish

## Peer dependencies problem when rendering HTML

- A hook which renders HTML [works well](https://github.com/osequi/react-css-perspective/blob/master/src/components/SquareMove/SquareMove.js) with Bit.dev and [breaks](https://github.com/osequi/use-controls) on npm packaging.
- The reason is peer / dev dependencies:
  - https://stackoverflow.com/questions/63892194/react-16-hooks-dont-work-in-nested-npm-package
  - https://developpaper.com/understanding-peer-dependencies/
- After fixing it another weird error came up: https://github.com/babel/babel/issues/12018
- This is too much devops.
- Bit.dev has a special React compiler solving all the devops: https://bit.dev/bit/envs/compilers/react/~code

