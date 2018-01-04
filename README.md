# yarn-version

This repository exists to demonstrate what appears to be a bug in [Yarn](https://yarnpkg.com/en/) 1.3.2.

Given:

* Windows 10
* [nodist](https://github.com/marcelklehr/nodist) 0.8.8
* Yarn 1.3.2
* PowerShell 5.1.15063.786

Clone this repository and run:

```
> nodist + 8.9.3
> nodist
> node -version
> yarn install
```

This will produce the following error message:

```
yarn install v1.3.2
info No lockfile found.
[1/5] Validating package.json...
error yarn-version@1.0.0: The engine "node" is incompatible with this module. Expected version "8.9.3".
error Found incompatible module
info Visit https://yarnpkg.com/en/docs/cli/install for documentation about this command.
```

Edit the `engines` section of `package.json` from:

```
  "engines": {
    "node": "8.9.3"
  }
```

to:

```
  "engines": {
    "node": "~8.9.0"
  }
```

and run `yarn install` again. No error.

Change `.node-version` to:

```
8.9.4
```

Change `engines` in `package.json` to:

```
  "engines": {
    "node": "8.9.4"
  }
```

Run:

```
> nodist + 8.9.4
> nodist
> node -version
> yarn install
```

No error.

Somehow Yarn on Windows doesn't think `'8.9.3' === '8.9.3'`.
  
  
