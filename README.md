# Probot: Commands

[![GitHub Actions](https://github.com/tidb-community-bots/probot-commands-pro/workflows/Test/badge.svg?branch=master)](https://github.com/features/actions)
[![Codecov](https://badgen.net/codecov/c/github/tidb-community-bots/probot-commands-pro?icon=codecov)](https://codecov.io/gh/tidb-community-bots/probot-commands-pro)
[![Probot](https://badgen.net/badge/built%20with/probot/orange?icon=dependabot&cache=86400)](https://probot.github.io/)
[![jest](https://facebook.github.io/jest/img/jest-badge.svg)](https://github.com/facebook/jest)
[![ISC License](https://badgen.net/badge/license/ISC/blue?cache=86400)](https://tidb-community-bots.isc-license.org)

> A [Probot](https://github.com/probot/probot) extension that adds slash commands to GitHub.

For example, from a comment box someone could type:

![Slash commands in a comment box](https://user-images.githubusercontent.com/173/30231736-d752e7dc-94b1-11e7-84bf-d8475733d701.png)

A Probot app could then use this extension to listen for the `remind` slash command.

## Installation

```
$ npm install --save probot-commands-pro
```

## Usage

```js
const commands = require('probot-commands-pro')

module.exports = robot => {
  // Type `/label foo, bar` in a comment box for an Issue or Pull Request
  commands(robot, 'label', (context, command) => {
    const labels = command.arguments.split(/, */);
    return context.github.issues.addLabels(context.issue({labels}));
  });
}
```

## Thanks
Powered by [commands](https://github.com/probot/commands)
