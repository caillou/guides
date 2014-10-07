# Git

## Global `.gitignore`

Every developer has their own tools and preferences. If you want to ignore some
files that are located inside a repository that are created by your tools and
preferences and not specific to that project (e.g. Mac OS X `.DS_Store` files or
editor specific files such as `*.sublime-project`) you should use a global
`.gitignore` file.

See [GitHub's help page][global gitignore] on how to configure git to use such
a global `.gitignore` file.

[global gitignore]: https://help.github.com/articles/ignoring-files#global-gitignore


## Npm install private repositories with SSH

Define your dependencies in the following way (tested with npm version 2.1.2):


```json
"dependencies": {
  "livingdocs-engine": "git+ssh://git@github.com:upfrontIO/livingdocs-engine.git"
}
```


## Npm install private repositories with HTTP

1. Install node.js and npm (http://nodejs.org/)
2. Install grunt using `npm install -g grunt-cli`
3. [Create a Github access token](https://help.github.com/articles/creating-an-access-token-for-command-line-use) for installing private repos.
4. From the root of the project run `npm install`. Note that Node packages must be defined like this in the `package.json` for this to work:

        "package": "git+https://github.com/upfrontIO/package"

5. Use your newly created token to login to Github (no password required). The login will be stored in your OSX keychain.
6. Add `osxkeychain` to your Git config: `git config --global credential.helper osxkeychain`
