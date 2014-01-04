# Versioning

Upfront uses the [Semantic Versioning](http://semver.org) system authored by
[Tom Preston Werner](http://tom.preston-werner.com/) (cofounder of Github). This
defines that a version number consists of three numeric characters, separated by
dots. Optionally to the version number is a identifier, which defines the build
version.

| 1     | . | 2     | . | 3     | - | alpha1     |
|:-----:|:-:|:-----:|:-:|:-----:|:-:|:----------:|
| major | . | minor | . | patch | - | identifier |

- MAJOR version when you make incompatible API changes,
- MINOR version when you add functionality in a backwards-compatible manner, and
- PATCH version when you make backwards-compatible bug fixes.
- Additional labels for pre-release and build metadata are available as
  extensions to the MAJOR.MINOR.PATCH format.

You can read more about this versioning scheme here:
[http://semver.org/](http://semver.org/)

## publish a new version
To push a new version, there are several things to do:

- update HISTORY.md with the newest changes. Prepend the changes to the file.
  
      0.1.1 / 2014-01-13
      ==================

      * make doc.toHtml() working, fixed in #75
      * allow interaction when using doc-html, fixed in #74

- create a new annotated tag: `git tag -a 0.1.1 -m 'version 0.1.1'`  
  (this can be done using a grunt module: [grunt-tagrelease](https://github.com/darsain/grunt-tagrelease))
- push the changes

## Dependencies

Besides the semantic versioning, dependencies should be referenced using the
minor version. In node environment this will be in a package.json file. In other
environments probably inside the library itself. Dependencies should always be
referenced by the minor version. Do not reference them by the PATCH version as
this version will change quickly and is anyways compatible to a minor version.
