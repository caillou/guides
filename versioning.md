# Versioning

Upfront uses the [Semantic Versioning](http://semver.org) system authored by [Tom Preston Werner](http://tom.preston-werner.com/) (cofounder of Github). This defines that a version number consists of three numeric characters, separated by dots. Optionally to the version number is a identifier, which defines the build version.

<table style="text-align:center;">
	<tr>
		<td>1</td><td>.</td><td>2</td><td>.</td><td>3</td><td>-</td><td>alpha1</td>	</tr>
	<tr>
		<td>|</td><td></td><td>|</td><td></td><td>|</td><td></td><td>|</td>	</tr>
	<tr>
		<td>major</td><td>.</td><td>minor</td><td>.</td><td>patch</td><td>-</td><td>identifier</td>	</tr>
</table>

- MAJOR version when you make incompatible API changes,
- MINOR version when you add functionality in a backwards-compatible manner, and
- PATCH version when you make backwards-compatible bug fixes.
- Additional labels for pre-release and build metadata are available as extensions to the MAJOR.MINOR.PATCH format.

You can read more about this versioning scheme here: [http://semver.org/](http://semver.org/)

create a tag in the current repo: `git tag -a 0.1.0 -m '0.1.0'`
push the tag to github: `git push origin 0.1.0`

# Dependencies
Besides the semantic versioning, dependencies should be referenced using the minor version. In node environment this will be in a package.json file. In other environments probably inside the library itself.
Dependencies should always be referenced by the minor version. Do not reference them by the PATCH version as this version will change quickly and is anyways compatible to a minor version.
