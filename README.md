# Temporary Containers+ Firefox Add-on

[![Temporary Containers Matrix room #tmp:mozilla.org](https://img.shields.io/badge/matrix-%23tmp%3Amozilla.org-blue)](https://matrix.to/#/#tmp:mozilla.org)

Detailed information about the Add-on [can be found in the wiki](https://github.com/temporary-containers-firefox/temporary-containers/wiki). There's also [this long-form article](https://medium.com/@stoically/enhance-your-privacy-in-firefox-with-temporary-containers-33925cd6cd21).

## Development

### Requirements

- Clone the repository
- `npm install`
- `npm run dev`

### Run in Firefox

- `npx web-ext run -s dist`
  - starts the default system Firefox with a temporary profile, loads the Add-on and watches for changes
  - append `-p profilename` to start Firefox with a specific profile

or

- Open `about:debugging` and `Load Temporary Add-on` which is located in the `dist` directory

Check `about:debugging` and click `Inspect` to the right of Temporary Containers to see the console.

### Run the tests

- Once: `npm test`
  - Shows a coverage summary and generates a detailed report in the `coverage` directory
- Watcher: `npm run watch:test`

### Release

#### AMO and GitHub

- Bump manifest version
- Commit, tag and push
- Upload zip web-ext-artifact to AMO
- Download published AMO xpi
- Create and publish GitHub release with AMO xpi

#### Pre-Release on GitHub

- Bump manifest version
- Commit and push
- git tag v1.0beta1
- git push origin v1.0beta1
- git log \$(git tag --sort=-version:refname | sed -n 2p)..HEAD --pretty=format:%s
- Add release notes and publish

## Libraries

[Vue.js](https://vuejs.org) and [SemanticUI](https://semantic-ui.com/) are used for the preferences & popup UI.

## License

MIT
