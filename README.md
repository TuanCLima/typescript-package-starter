# TypeScript Package Starter

A minimal npm-package publishing exercise with TypeScript source, ESM and CommonJS builds, generated declarations, tests and Changesets releases.

The exported `add` function is deliberately simple: this repository demonstrates package tooling rather than a substantial utility library. The GitHub repository is named `typescript-package-starter`; the existing npm package name remains `my-test-package` for compatibility.

## Tooling

| Purpose                        | Tool                 |
| ------------------------------ | -------------------- |
| ESM, CommonJS and declarations | tsup                 |
| Type checking                  | TypeScript           |
| Unit tests                     | Vitest               |
| Formatting                     | Prettier             |
| Export compatibility           | Are the Types Wrong? |
| Versions and changelog         | Changesets           |
| Continuous integration         | GitHub Actions       |

## Develop locally

Use Node.js 22 and npm:

```bash
git clone https://github.com/TuanCLima/typescript-package-starter.git
cd typescript-package-starter
npm ci
npm run ci
```

`npm run ci` builds the package, checks formatting and export compatibility, type-checks the source and runs tests. `npm run dev` runs Vitest in watch mode.

## API example

After building, from this repository:

```js
import { add } from './dist/index.js';
console.log(add(2, 3)); // 5
```

The source API is in `src/utils.ts`; `src/index.ts` exports it. `tsup.config.ts` defines both build formats and generated type declarations.

## Release workflow

Use `npx changeset` to describe a change and commit its changeset file. The `local-release` script versions and publishes the package to npm, so run it only when intentionally publishing with the correct registry account. It is not required for local development or CI.

See [CHANGELOG.md](CHANGELOG.md) for the existing release history.

## License

[MIT](LICENSE).
