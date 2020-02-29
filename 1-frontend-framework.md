# 1. Frontend framework

## Status

accepted

## Context

We need frontend for zagrajmy.

We've considered TypeScript+Svelte+Sapper and TypeScript+React+Next.
We didn't consider JavaScript, because Piotrek, the main person who'll write the frontend is addicted to intellisense.

### TypeScript

#### Pros

- correctness
- better DX

#### Cons

- Piotrek will eagerly contribute to DefinitelyTyped whenever he finds problem with library typings

### Svelte and Sapper

#### Pros

- Sapper is pretty cool, easy to write and generates super performant apps. Compilers are the new frameworks, yeah.

#### Cons

- Svelte is still pretty fresh and and the TypeScript support is immature

### React and Next

#### Pros

- React has a huge ecosystem.
- Piotrek is familiar with Next. We have limited time, so we need boring sources.
- Next has a purpose-build cloud hosting (Zeit Now). Frontend continous deployment and staging will just work (tm).

#### Cons

- Pretty high learning curve for new contributors unfamiliar with React.

## Decision

We've chosen React and NextJS.

## Consequences

We won't land on "hot svelte apps" website.
