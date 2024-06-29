📦🚀 semantic-release
Fully automated version management and package publishing
Join the community on GitHub Discussions Build states OpenSSF Scorecard semantic-release: angular

npm latest version npm next version npm beta version

semantic-release automates the whole package release workflow including: determining the next version number, generating the release notes, and publishing the package.

This removes the immediate connection between human emotions and version numbers, strictly following the Semantic Versioning specification and communicating the impact of changes to consumers.

Trust us, this will change your workflow for the better. – egghead.io

Highlights
Fully automated release
Enforce Semantic Versioning specification
New features and fixes are immediately available to users
Notify maintainers and users of new releases
Use formalized commit message convention to document changes in the codebase
Publish on different distribution channels (such as npm dist-tags) based on git merges
Integrate with your continuous integration workflow
Avoid potential errors associated with manual releases
Support any package managers and languages via plugins
Simple and reusable configuration via shareable configurations
Support for npm package provenance that promotes increased supply-chain security via signed attestations on GitHub Actions
How does it work?
Commit message format
semantic-release uses the commit messages to determine the consumer impact of changes in the codebase. Following formalized conventions for commit messages, semantic-release automatically determines the next semantic version number, generates a changelog and publishes the release.

By default, semantic-release uses Angular Commit Message Conventions. The commit message format can be changed with the preset or config options of the @semantic-release/commit-analyzer and @semantic-release/release-notes-generator plugins.

Tools such as commitizen or commitlint can be used to help contributors and enforce valid commit messages.

The table below shows which commit message gets you which release type when semantic-release runs (using the default configuration):

Commit message	Release type
fix(pencil): stop graphite breaking when too much pressure applied	Patch Fix Release
feat(pencil): add 'graphiteWidth' option	Minor Feature Release
perf(pencil): remove graphiteWidth option

BREAKING CHANGE: The graphiteWidth option has been removed.
The default graphite width of 10mm is always used for performance reasons.	Major Breaking Release
(Note that the BREAKING CHANGE:  token must be in the footer of the commit)
Automation with CI
semantic-release is meant to be executed on the CI environment after every successful build on the release branch. This way no human is directly involved in the release process and the releases are guaranteed to be unromantic and unsentimental.

Triggering a release
For each new commit added to one of the release branches (for example: master, main, next, beta), with git push or by merging a pull request or merging from another branch, a CI build is triggered and runs the semantic-release command to make a release if there are codebase changes since the last release that affect the package functionalities.

semantic-release offers various ways to control the timing, the content and the audience of published releases. See example workflows in the following recipes:

Using distribution channels
Maintenance releases
Pre-releases
Release steps
After running the tests, the command semantic-release will execute the following steps:

Step	Description
Verify Conditions	Verify all the conditions to proceed with the release.
Get last release	Obtain the commit corresponding to the last release by analyzing Git tags.
Analyze commits	Determine the type of release based on the commits added since the last release.
Verify release	Verify the release conformity.
Generate notes	Generate release notes for the commits added since the last release.
Create Git tag	Create a Git tag corresponding to the new release version.
Prepare	Prepare the release.
Publish	Publish the release.
Notify	Notify of new releases or errors.
Requirements
In order to use semantic-release you need:

To host your code in a Git repository
Use a Continuous Integration service that allows you to securely set up credentials
A Git CLI version that meets our version requirement installed in your Continuous Integration environment
A Node.js version that meets our version requirement installed in your Continuous Integration environment
Documentation
Usage
Getting started
Installation
CI Configuration
Configuration
Plugins
Workflow configuration
Shareable configurations
Extending
Plugins
Shareable configuration
Recipes
CI configurations
Git hosted services
Release workflow
Developer guide
JavaScript API
Plugins development
Shareable configuration development
Support
Resources
Frequently Asked Questions
Troubleshooting
Node version requirement
Node Support Policy
Get help
GitHub Discussions
Stack Overflow
Twitter
