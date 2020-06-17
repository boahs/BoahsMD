---
title: "package.json explained"
path: "/package_json"
date: "2020-06-17"
coverImage: ""
author: "Boahs"
excerpt: '"Your standard node.js project contains a file called package.json..."'
tags: ["js", "json", "node", "learning"]
---
## Json is easy! 

You might notice "package.json" inside every node.js project you've seen and wonder "What exactly is this, and why does every project have one?". Simply put it's a JSON manifest file which is meant to hold all relevant data to that project. Just like how the owner of a small car repair shop holds all his information about his business, the clients he has, and the different vendors he uses to get his parts. 

Your typical package.json will look like this example: 

```json
{
  "name": "Example project", 
  "description": "To show readers a clear demostration of how package.json works",
  "version": "0.0.1",
  "author": "Boahs <boahs@boahs.info>",
  "dependencies": {...},
  "keywords": [
    "keywords",
    "for seo",
    "can be entered here"
  ],
  "license": "MIT",
  "scripts": {...},
  "devDependencies": {...},
  "repository": {
    "type": "git",
    "url": "https://github.com/boahs"
  }
}
```

* <b>Version</b> --- "1.2.3" The 1 is the release version, the 2 will be the minor version, and the 3 is the patch version. 

* <b>Scripts</b> --- Here you can list any scripts you may be using in your project. These can be building scripts, deployment scripts etc. 

* <b>devDependencies</b> --- The dependencies only needed for dhe development side of the project. Not to be confused with <b>"dependencies"</b>. 

* <b>dependencies</b> These are required for building your project. Be sure you're including what version of what dependency you're using like this <b>"gatsby-cli": "^2.7.47"</b> 

If you're wanting to initialize your very own package.json inside your projects home directory simply follow these steps:

```powershell
cd...{directory}
```

```powershell
npm init
```

```powershell
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help json` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg>` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
package name: example_name
version: (0.0.1)
description:Cool my first json package
entry point: (index.js)
test command:
git repository:
keywords:
author:
license: (ISC)
About to write to .\package.json:

{
  "name": "example_name",
  "version": "0.0.1",
  "description": "Cool my first json package",
  "main": "index.js",
  "scripts": {
    "test": "echo \"" && exit 1"
  },
  "author": "",
  "license": "ISC"
}


Is this OK? (yes)
```

I'll leave it up to you to fill out the proper information you need! Once you have initialized your first package.json file you'll notice <b>package-lock.json</b> is also generated. These are files generated automatically for any operations where npm modifies either the <i>node_modules</i> tree, or package.json. It's to ensure the program will work on different machines. 

<b><u>This file is never to be edited by hand!</u></b>

Json is a lot simplier than you thought, and a really neat way to keep node happy! So we've concluded that package.json is the manifest of a node.js project, and package-lock.json will store the exact same package so it may work on other machines properly. 

Thank you for reading! 

**— Boahs**