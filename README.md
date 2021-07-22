# yarn-monorepo-sourcemap-repro

Repro for a debugging problem with yarn PnP in a TypeScript monorepo.

We have two packages `a` and `b`. Both should have a breakpoint in their `index.ts` file.
`test.ts` imports both, package `a` via its package name, package `b` via its relative path.

If you the repo in VSCode and execute `yarn debug` in a debug terminal, you'll see that the breakpoint in `b/src/index.ts` is resolved and debugging steps into there,
but in `a`, the breakpoint is not resolved and debugging uses the compiled `index.js` file.