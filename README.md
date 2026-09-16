# TypeScript Package Template

- [pnpm](https://pnpm.io/) - Package manager
- [Vitest](https://vitest.dev/) - Testing framework
- [Rollup](https://rollupjs.org/) - Module bundler
- [ESLint](https://eslint.org/) - Linter
- [Prettier](https://prettier.io/) - Code formatter
- [Husky](https://typicode.github.io/husky/) - Git hooks
- [lint-staged](https://github.com/okonet/lint-staged) - Run linters on git staged files
- [commitlint](https://commitlint.js.org/) - Conventional commit messages
- [release-please](https://github.com/googleapis/release-please) - Automated releases

## Releasing

Releases are created by [release-please](https://github.com/googleapis/release-please) and published to npm with
[trusted publishing](https://docs.npmjs.com/trusted-publishers) and [staged publishing](https://docs.npmjs.com/staged-publishing),
so no npm token is stored in the repository.

One-time setup on npmjs.com, under the package's _Settings → Trusted publisher_:

- Publisher: GitHub Actions
- Organization/user: the repository owner
- Repository: this repository
- Workflow filename: `release.yml`

Every release run stages the tarball instead of publishing it. To ship it, a maintainer approves the staged version
with 2FA — on npmjs.com or with `npm stage approve <stage-id>` (`npm stage list` shows what is pending,
`npm stage reject <stage-id>` discards it).
