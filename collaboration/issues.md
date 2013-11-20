# Issues

This guide documents how we use GitHub issues in our repositories.

## Labeling

Issues should have exactly one label. The labels we use are:

- **bug**: Well, this one is the most obvious. Favorably the title should
  start with 'Bug:' since the label will disappear when the issue is transformed
  into a pull-request.

- **discussion**: Discussions about future features, workflows, technical
  challenges, research, or even spike solutions should be labeled with
  discussion. Ideally the title is a question or makes it clear that the issue
  is an open discussion like "Proposal for ...". In discussions you can bring in
  all your crazy ideas.

- **feature**: Focused on the implementation of additional functionality. It
  should be relatively clear what is to do and the discussion should be focused
  on the implementation. Ideas for the future should only be discussed if they
  can have a profound impact on how to approach the problem right now. The
  assigned developer should have the last word if there is a dispute and
  development is already underway.

- **refactoring**: Everything that concerns project setup, code quality and code
  readability should go in this category.

## Pull-Requests

Issues of type 'bug', 'feature' and 'refactoring' can all be transformed into pull-requests.
And in fact this is the preferred way of creating a pull-request. To do that you can use
git's [hub](https://github.com/github/hub) command line wrapper. Look for the command `git pull-request`.

## Assign Persons

As soon as you start developing on an issue assign yourself to it, so that others can see 
the issue is already worked on. Unassign yourself if you stop working on the issue and explain
the status of the issue in a comment. If you finished implementing the issue you can leave yourself
assigned.
