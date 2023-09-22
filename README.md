**licensetool** is a license tool for web frontend.

# Usage

* Add licensetool to your NPM dependency:

```console
$ npm install --save-dev github:pfnet/licensetool
```

* Output a concatenated license notices of the dependency NPM packages:

```console
$ npx licensetool format --config licensetool.json
$ npx licensetool format --config licensetool.json --output csv # Output as csv
```

# `licensetool.json`

* `packages`

Override the properties of the specified packages.
If some properties or a whole package entry is missing from `packages`, those retrieved by [license-checker-rseidelsohn](https://github.com/RSeidelsohn/license-checker-rseidelsohn) and other libraries are used.


* `packages.omit`

Omit this package from the license notices.

```json
{
  "packages": {
    "somepackage@1.0.0": {
      "omit": true
    }
  }
}
```

* `packages.licenseId`

Specify the SPDX ID.

```json
{
  "packages": {
    "somepackage@1.0.0": {
      "licenseId": "MIT"
    }
  }
}
```


* `packages.licenseName`

Specify the license name.

```json
{
  "packages": {
    "somepackage@1.0.0": {
      "licenseName": "Modified MIT"
    }
  }
}
```


* `packages.licenseFile`

Specify the file whose contents is the license text.
If `null` is given, it invalidates the corresponding property retrieved by license-checker-rseidelsohn, which leads to using the default license notice of the resolved SPDX.

```json
{
  "packages": {
    "somepackage@1.0.0": {
      "licenseFile": "path/to/license-notice.txt"
    }
  }
}
```

```json
{
  "packages": {
    "somepackage@1.0.0": {
      "licenseFile": null
    }
  }
}
```

* `packages.licenseContent`

Directly specify the content of license notice.

```json
{
  "packages": {
    "somepackage@1.0.0": {
      "licenseContent": "Some Package License\n\nCopyright (C) 2023 John Doe\n\nSome license notice sentences"
    }
  }
}
```
