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

## Publishing a new version

To push a new version, there are several things to do:

1. **Build the project**  
  Run the projects build task and make sure all the tests pass. It is recommended to setup the build task so tests, linting and such are automatically run.

2. **Update the Changelog**  
  Update Changelog.md or HISTORY.md or with the newest changes. Prepend the changes to the file. Link to all merge pull requests.

  Example Changelog.md:
  ```markdown
  # v0.1.2 (2014-03-07)

  - [Add selection methods](https://github.com/upfrontIO/Editable.JS/pull/64)
    - New Selection methods:  
      #collapseAtBeginning()  
      #collapseAtEnd()
    - New Cursor and Selection method:  
      #setVisibleSelection() (alias for #setSelection())

  # v0.1.1 (2014-01-24)

  - Setup Versioning
  ```

3. **Release**  
  Every project should have a grunt release task that can be called with `:patch`, `:minor`, and `:major`. The release task creates a tag, updates versions in the relevant files (package.json and bower.json) and commits and pushes all changes. For more info check out [grunt-bump](https://github.com/vojtajina/grunt-bump).

  ```bash
  # Example for a batch release
  grunt release:patch
  ```


## Working with tags manually

```bash
# delete a tag locally
git tag -d v1.2

# delete a tag locally
git push origin :refs/tags/v1.2

# create a new annotated tag
git tag -a v0.1.1 -m 'Version 0.1.1'

# push tags
git push --tags
```


## Declaring Versions of Dependencies

Besides the semantic versioning, dependencies should be referenced using the
minor version. In node environment this will be in a package.json file. In other
environments probably inside the library itself. Dependencies should always be
referenced by the minor version. Do not reference them by the PATCH version as
this version will change quickly and is anyways compatible to a minor version.
