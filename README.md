# braintree-ios-issue-demo

Demonstraition of reproduction of [Issue 484](https://github.com/braintree/braintree_ios/issues/484)

## Project Setup:
Provide a small project with a similar setup of integrating Braintree-iOS via Carthage submodules

### Steps
1. Clone repo with SSH (scripts use ssh)
2. run setup script `bin/init` which installs Homebrew/Carthage

This initial project is sestup to use my forks as commiting a dirty repo is problematic and is easier to be seen in person when updating to the latest braintree-ios release.

## How to Repro a Dirty dependency
Initial Repo is running with my fork which shows a clean resolved cartfile as well as submdule.

### Steps
- Open [Cartfile](https://github.com/dmiluski/braintree-ios-issue-demo/blob/master/Cartfile#L2) to edit
- Comment out my forks in favor of braintree's leaving only the braintree dependencies

```
# Dependencies which dirty our repo
 github "braintree/braintree_ios" ~> 4.0
 github "braintree/braintree-ios-drop-in" ~> 7.0
```

- Run `bin/update` which updates the dependencies to latest. This should yield submodules, Cartfile.resolved, .gitmodules being updates. Of which, the only issue is in the braintree-ios submodule directory being dirt for reasons mentioned in the issue.

