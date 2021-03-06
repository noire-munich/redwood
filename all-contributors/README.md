# All-Contributors
<!-- toc -->
- [Purpose and Vision](#Purpose-and-Vision)
- [Package Lead](#Package-Lead)
- [Managing All-Contributors Data](#step-2-merge-contributors-into-main-file)
- [Roadmap](#Roadmap)
- [Contributing](#Contributing)

## Purpose and Vision
Redwood has a vibrant community that we want to highlight as much as possible. Using the [All-contributors](https://allcontributors.org/) specifications and CLI, this project allows us to:
- track the Framework, create-redwood-app, and Redwoodjs.com repo contributors
- display the aggregated list of contributors in the [Contributors section](https://github.com/redwoodjs/redwood/blob/main/README.md#contributors) of the root README.md

## Lead
[@thedavidprice](https://github.com/thedavidprice)

## Managing All-Contributors Data
In general, this is a three-part process:
1. Update the three `*.all-contributorsrc` files with new contributors
2. Merge changes into the main `.all-contributorsrc` file
3. Update README.md#Contributors with changes

**FILES**  
**Framework** `redwoodjs/redwood` project:  
_note: this file is also used for all aggregated contributors_  
- `.all-contributorsrc`

**CRWA** `redwoodjs/create-redwood-app` project:
- `.crwa.all-contributorsrc`

**Website** `redwoodjs/redwoodjs.com` project:
- `.rwjs.com.all-contributorsrc`

>When adding contributors, use this "type" key for specific repos:
>- 💻 (code) == Framework
>- 📖 (doc) == Redwoodjs.com
>- 🔧 (tool) == Create-Redwood-App
>
>The "type" is required.

### Step 1: Check for new contributors and add to `*rc` files

#### Framework
```js
yarn all-contributors check --config ./all-contributors/.all-contributorsrc

// For each contributor listed in output, repeat the following:

yarn all-contributors add --config ./all-contributors/.all-contributorsrc <contributor> code
```

#### Redwoodjs.com
```js
yarn all-contributors check --config ./all-contributors/.rwjs.com.all-contributorsrc

// For each contributor listed in output, repeat the following:

yarn all-contributors add --config ./all-contributors/.rwjs.com.all-contributorsrc <contributor> doc
```

#### Create-Redwood-App
```js
yarn all-contributors check --config ./all-contributors/.crwa.all-contributorsrc

// For each contributor listed in output, repeat the following:

yarn all-contributors add --config ./all-contributors/.crwa.all-contributorsrc <contributor> tool
```

### Step 2: Merge contributors into main file
This script will add contributors from Redwoodjs.com and CRWA repos into the Framework file (if they don't already exist). It will also update the "type" of contribution for existing contributors.

```bash
node mergeContributors.js
```

### Step 3: Update the content in README.md#Contributors
```bash
yarn all-contributors generate --config all-contributors/.all-contributorsrc
```

Don't forget to commit and PR changes.

## Roadmap
- [ ] Create a script to handle Step 1 (check and add new contributors for each repo)
- [ ] Convert these scripts into a GH Action that runs daily

## Contributing
Help with this project is welcome and needed! No specific experience required. You'll want to be familiar with:
- All-contributors [config](https://allcontributors.org/docs/en/cli/configuration) and [CLI](https://allcontributors.org/docs/en/cli/usage)
- [GH Actions (Node.js)](https://docs.github.com/en/actions/language-and-framework-guides/using-nodejs-with-github-actions)
