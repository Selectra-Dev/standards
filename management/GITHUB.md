GitHub
=

# Table of contents

1. [Naming convention](#naming-convention)

2. [Workflow](#workflow)

    2.1. [Default workflows](#default-workflows)

    2.2. [Extended workflow](#extended-workflows)

3. [Commits](#commits)

    3.1. [When do I need to commit?](#when-do-i-need-to-commit)

    3.2. [How do I write my commits](#how-do-i-write-my-commits)

# Naming convention

- **SHOULD** kebab-case for repository name

    > If it's technically impossible, use snake_case.

- API Client repository **MUST** consist of programming language name and follow [`api-{language}-client-{name}`](https://github.com/Selectra-Dev?utf8=✓&q=*-api-*-client) pattern

    > Most of the libraries we create [aren't SDK's](https://github.com/Selectra-Dev/standards/issues/8). If they're containing integration tools (like debugger's, helpers or view generators), you can consider them SDK and call repository `sdk-{language}-{name}`.

# Workflow

We use two different types of workflow depending on the project size. For most of our projects, we stick to the one we refer to as "Default workflows". However, for bigger projects, we might opt for the extended one.

The choice of either of these workflows is open to discussion, but **MUST** be made in agreement with the whole developing team and the sysadmin.

The chosen workflow **MUST** be one of these two choices. Having consistent use of GitHub across our projects helps preventing mistakes, and makes the developer's work easier.

## Default workflows

By default, we simply follow GitHub guidelines:
- The shared repository on GitHub has one permanent branch: master. The content of this branch **MUST** always be deployable;
- When working on a new fix or feature, the developer **MUST** create a new branch on the shared repository. It is **RECOMMENDED** that the developer commits and push his work on this branch regularly in order to keep a clean and useful history;
- When a bug is found on the application, an issue **MUST** be created on GitHub and provide explainations on how to reproduce it. Screenshots **SHOULD** be given as well to help debugging. A developer **MUST** be assigned to the issue in order to fix the bug. Labels **CAN** be provided to help prioritizing the issues. Finally, the commit that fix the bug **MUST** start with "Fix #[ID_OF_THE_ISSUE]:".
- When the code is ready to be deployed, or when the developer wants to discuss some details concerning new features, he **MUST** create a pull request. He **MUST NOT** merge directly to master;
- When the team agrees on the changes, the project manager merges the branch into master.

The guidelines for Github Flow can be found [here](https://guides.github.com/introduction/flow/).

## Extended workflow

For some projects, it might be useful to use a more complex workflow. The complete guideline is available [here](http://nvie.com/posts/a-successful-git-branching-model/)

# Commits

## When do I need to commit?

Commits on the public repository **MUST** follow the atomic approach:
- Commit each fix or task as a separate change
- Only commit when a block of work is complete
- Commit each layout change separately
- Joint commit for layout file, code behind file, and additional resources

The goal is to be able to easily roll back a specific change, without affecting the others. However, you **SHOULD NOT** commit unstable work. If you need to commit some unstable code to safeguard your work, do it on a local branch, and clean it up before merging to your master branch and pushing to the remote repository. [This article](https://sandofsky.com/blog/git-workflow.html) provides some good guidelines on the subject.

## How do I write my commits

Here are 7 rules you **MUST** respect when writing a commit:
- Separate subject from body with a blank line
- Limit the subject line to 50 characters
- Capitalize the subject line
- Do not end the subject line with a period
- Use the imperative mood in the subject line
- Wrap the body at 72 characters
- Use the body to explain what and why vs.

A good rule of thumb is to check if your commit subject could complete the sentence "If applied, this commit will..."

Ex:
- `If applied, this commit will changing behavior of X` :x:
- `If applied, this commit will more fixes for broken stuff` :x:
- `If applied, this commit will remove deprecated methods` :white_check_mark:

You can find more on the subject [in this article](https://chris.beams.io/posts/git-commit/) from which these guidelines are taken.
