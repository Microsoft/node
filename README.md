﻿Node.js on ChakraCore
===
This project enables Node.js to optionally use the ChakraCore JavaScript engine. This project is still **work in progress** and not an officially supported Node.js branch. Please refer to the original [PR](https://github.com/nodejs/node/pull/4765).

### How it works

To enable building and running Node.js with the ChakraCore JavaScript engine, a V8 API shim (ChakraShim) is created on top of the ChakraCore runtime hosting API ([JSRT]
(https://msdn.microsoft.com/en-us/library/dn249673(v=vs.94).aspx)). ChakraShim implements the most essential V8 APIs so that the underlying JavaScript engine change is transparent to Node.js and other native addon modules written for V8.

A rebuild node.exe and native addon modules with ChakraCore is required for this to work.

### Issues
Please report all issues related to Node-ChakraCore on this separate [issue page](https://github.com/nodejs/node-chakracore/issues).

### Prebuilt Node binaries
You can download and install prebuilt Node-ChakraCore from [here](https://github.com/nodejs/node-chakracore/releases).

### How to build
If you are looking to build this yourself. Here's what you will need.

Prerequisites:
* Windows 7 SP1 or higher (Windows 8.1 or higher for ARM builds)
* [Python 2.6 or 2.7](https://www.python.org)
* [Visual
Studio](https://www.visualstudio.com/en-us/downloads/download-visual-studio-vs.aspx)

Build Command:
```batch
vcbuild chakracore nosign [x86|x64|arm]
```

### How to test

```batch
vcbuild chakracore nobuild test [x86|x64|arm]
```

To test if Node.js was built correctly with ChakraCore:

```batch
C:\>node -e "console.log('Hello from Node.js ' + process.jsEngine)"
Hello from Node.js chakracore
```

## Resources for Newcomers

* [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md)
* [CONTRIBUTING.md](./CONTRIBUTING.md)
* [GOVERNANCE.md](./GOVERNANCE.md)

## Current Project Team Members

This project is maintained by the members of the [nodejs/node-chakracore]
(https://github.com/orgs/nodejs/teams/node-chakracore) team. 
[Team members from the Node.js project]
(https://github.com/nodejs/node#current-project-team-members) are also
considered Collaborators with respect to [COLLABORATOR_GUIDE.md]
(./COLLABORATOR_GUIDE.md) and [GOVERNANCE.md](./GOVERNANCE.md), however
they are not required nor expected to actively maintain this project.
