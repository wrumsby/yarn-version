# yarn-version

This repository exists to demonstrate what appears to be a bug in Yarn 1.3.2.

If `engines.node` is `8.9.3` in `package.json` running `yarn install` on Windows will produce the following error message:

```
yarn install v1.3.2
info No lockfile found.
[1/5] Validating package.json...
error yarn-version@1.0.0: The engine "node" is incompatible with this module. Expected version "8.9.3".
error Found incompatible module
info Visit https://yarnpkg.com/en/docs/cli/install for documentation about this command.
```
