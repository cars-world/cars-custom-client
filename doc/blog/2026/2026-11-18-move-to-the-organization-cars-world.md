<!--
@license
Copyright (c) rljson

Use of this source code is governed by terms that can be
found in the LICENSE file in the root of this package.
-->

# Move to the organization cars-world

## Motivation

- `cars-custom-client` now lives in the GitHub organization
  [cars-world](https://github.com/cars-world), which holds the repos of
  the cars application
- GitHub forwards the old address `rljson/cars-custom-client`, but only as long as no
  new repo takes that name; links and installs should not depend on it
- The package name should say where the package lives

## Strategy

- Change every name that points to the organization, nothing else
- The package becomes `@cars-world/cars-custom-client`
- The Rljson libraries it uses keep their scope `@rljson`
- The license headers stay as they are
- No change in behavior: the same code, the same tests

## Names

- `package.json`: `name`, `homepage`, `bugs` and `repository` name
  `cars-world`
- `index.jsonc` carries the new package name
- The README, in English and German: title, CI badge, the install line
  `pnpm add git+ssh://git@github.com/cars-world/cars-custom-client.git` and the imports
- The comment of the version constant names `@cars-world/cars-custom-client`

## Result

- The package is `@cars-world/cars-custom-client`; all links lead to `cars-world`
  without a detour
- `pnpm test` passes with 100 percent coverage

## Open Points

- Whoever imports the package switches to `@cars-world/cars-custom-client` with the
  next release
- The image keeps its name `cars-custom-client` in the registry `crcars`
