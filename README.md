

<h3 align="center"> <a href="https://codelingo.io" target="_blank">
    <img src="./public/img/CLLogo.svg" />
  </a> </h3>

<p align="center">
  <b>Drive Continuous Higher Standards with CodeLingo's Automated Reviews, Bug Fixes and Docs! </b>
</p>

<p align="center">
  <a href="https://github.com/apps/codelingo" target="_blank">
    <img width="295" height="38" src="https://raw.githubusercontent.com/codelingo/codelingo/master/public/img/install.png" />
  </a>
</p>

## Overview

CodeLingo finds and fixes issues in existing code and ensures the same issues don't sneak in with new pull requests. CodeLingo also generates your contributor docs thus automating three cornerstones (bug fixing, reviewing and doc updates) to scale up your code quality.


<!-- TODO CLQL tutorial -->

## @CodeLingoBot Quick Start

@CodeLingoBot fixes bugs, automates code reviews and updates contributor docs for repos on GitHub based on rules, called Rules, defined in codelingo.yaml files. There are several ways you can interact with @CodeLingoBot. The simplest is to trigger actions by commenting on a Pull Request:

+ `@CodeLingoBot review` reviews the PR based on default Rules for the repo's language or custom Rules added in a codelingo.yaml file in the root of the repo. <details><summary>You can trigger CodeLingo actions by replying to comments generated by`@review`</summary>
    + `@CodeLingoBot review ignore [reason]` ignores the issue for current and future reviews with an optional reason why.
    + `@CodeLingoBot review un-ignore` un-ignores the issue for current and future reviews.
+ `@CodeLingoBot rewrite` makes a PR to this PR fixing the issues found based on default Rules for the repo's language or custom Rules added in a codelingo.yaml file in the root of the repo. <details><summary>You can trigger CodeLingo actions by replying to comments generated by`@rewrite`</summary>
  
    + `@CodeLingoBot rewrite set <varname>` sets the value of a variable in a rewrite template.

To have @CodeLingoBot automatically review every new Pull Request to your repo, [install CodeLingo on your repo](https://github.com/apps/codelingo). If you don't already have a codelingo.yaml file, @CodeLingoBot will make a PR to add one to your repo. This will contain a bundle of Rules based on the languages in your repo.

Every pull request to your repository will now be checked against the go Rule bundle we imported above:

<p align="center">
<img src="https://raw.githubusercontent.com/codelingo/codelingo/master/public/img/cl_review2.png" />
</p>

### Editing codelingo.yaml

Let @CodeLingoBot know what Rules you'd like it to enforce by adding or
removing them from codelingo.yaml. You can find Rules to add using the [CodeLingo
Dashboard](https://dash.codelingo.io). For example, if we wanted to install the "go" bundle written by "codelingo" we'd update the codelingo.yaml as follows:

```yaml
# codelingo.yaml file

rules:
  - import: codelingo/go
```

## Power Users!

The rest of this README is for users interested in writing their own Rules and testing out CodeLingo on repositories on their local machine.

### Contributing a Rule or Rule Bundle

The Rule bundles that are rendered on codelingo.io/Rules are populated by the Rules in the [Rules directory](https://github.com/codelingo/codelingo/tree/master/tenets) in this repository. Contributing a new Rule is simply a matter of making a PR to this repo. We're a young community of Rule authors eager to help and guide you through your first PR.

Get started with the [docs](https://www.codelingo.io/docs) and find us at [codelingo.slack.com](https://codelingo.slack.com)!

### Writing a Rule

#### Playground

Each Rule has a `query`, written in [CLQL](https://www.codelingo.io/docs/concepts/CLQL/), to match a pattern. The online [playground](https://codelingo.io/playground) is a quick way to test and learn CLQL. It has a box of source code next to a box of CLQL. Select the source code and the playground will automatically generate the CLQL to match that selection!

<p align="center">
  <a href="https://codelingo.io/playground" target="_blank">
    <img src="https://raw.githubusercontent.com/codelingo/codelingo/master/public/img/cl_sandbox.png" />
  </a>
</p>

#### Setting up CodeLingo on your Dev Box

Before we get into writing Rules, we want to ensure we can run and test them locally. For this, we're going to use the lingo CLI tool to run a review on our local machine. First, install the [lingo CLI](https://github.com/codelingo/lingo/releases/latest) and set it up with the following commands:

```bash
# Run this command from anywhere. Follow the prompts to set up Codelingo on your machine.
$ lingo config setup

# Run this command inside a git repository to add a default codelingo.yaml file in the current directory.
$ lingo init
```

Replace the content of the codelingo.yaml file we wrote above with:

```yaml
  rules:
    - import: codelingo/go
```

You can now run the review to check your source code against the go Rule bundle we imported above.

```bash
# Run this command from the same directory as the codelingo.yaml file or any of its sub directories.
$ lingo run review
```

<p align="center">
<img src="https://raw.githubusercontent.com/codelingo/codelingo/master/public/img/cl_local_review.png" />
</p>

## Next Steps

Visit your [CodeLingo Dashboard](https://dash.codelingo.io)

You now have the tools setup to start writing your own Rules! See the [getting started guide](https://www.codelingo.io/docs/#getting-started) to learn more about Rules and how to write them.

## Resources

### Community

<!-- TODO slack numbers -->

 - [slack](https://join.slack.com/t/codelingo/shared_invite/enQtNDYxOTYyNTI5NjUwLWFiNjFjOTM3YzgzMjA4NjNiNDhmN2RkZWNlODM0ZTM5NTkzOThhZjczN2ZlYmNkMjhkNDBkYjBlMjQ1NDk2NTQ)
 - [hello@codelingo.io](mailto:hello@codelingo.io)

### Learn

- [codelingo.io/playground](https://codelingo.io/playground) - Write, automatically generate and run Rules and Flows online.
- [codelingo.io/docs](https://codelingo.io/docs) - Learn to write (and automatically generate!) Rules and compose Flows.

### Repos 

- [github.com/codelingo/lingo](https://github.com/codelingo/lingo) - CLI client for Codelingo.
- [github.com/codelingo/ideplugins](https://github.com/codelingo/ideplugins) - Run Flows directly in your IDE (Note: WIP).

<!-- TODO: add these
- [github.com/codelingo/lexiconsdk](https://github.com/codelingo/lexiconsdk) - Add support for new Lexicons
- [github.com/codelingo/flowsdk](https://github.com/codelingo/flowsdk)
-->

<!-- TODO: lexiconsdk -->

## About Us

We are a small **VC backed** development team from 🥝 **New Zealand** with a passion for the art of software development in itself!

Check out our team here: <a href="https://www.codelingo.io/about" target="_blank">codelingo.io/about</a>.
