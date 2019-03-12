# Release Utils

## Install

`npm install @tryghost/release-utils --save`

or

`yarn add @tryghost/release-utils`


## Usage

Create Gist:

```
const releaseUtils = require('@tryghost/release-utils');


releaseUtils
    .gist
    .create({
        userAgent: String,
        gistName: String,
        gistDescription: String,
        changelogPath: String [Path on Disk]
        github: {
            username: String
            token: String
        },
        isPublic: Boolean [optional, Default: true]
    })
```

Create Changelog:

```
const releaseUtils = require('@tryghost/release-utils');


const changelog = new releaseUtils.Changelog({
    changelogPath: String [Path on Disk],
    folder: String [Path on Disk]
});

changelog
    .write({
        githubRepoPath: String,
        lastVersion: String
    })
    .write({
        githubRepoPath: String
        lastVersion: String
        append: Boolean [optional, Default: false],
        folder: String
    })
    .sort()
    .clean()
```

Create Release:

```
const releaseUtils = require('@tryghost/release-utils');


releaseUtils
    .releases
    .create({
        tagName: String,
        releaseName: String,
        userAgent: String,
        uri: String,
        github: {
            username: String,
            token: String,
        },
        changelogPath: String [Path on Disk],
        gistUrl: String [optional],
        preRelease: Boolean [optional, Default: false],
        draft: Boolean [optional, Default: true],
        filterEmojiCommits: Boolean [optional, Default: true]
    });
```


## Develop

This is a mono repository, managed with [lerna](https://lernajs.io/).

Follow the instructions for the top-level repo.
1. `git clone` this repo & `cd` into it as usual
2. Run `yarn` to install top-level dependencies.


## Run

- `yarn dev`


## Test

- `yarn lint` run just eslint
- `yarn test` run lint and tests




# Copyright & License

Copyright (c) 2019 Ghost Foundation - Released under the [MIT license](LICENSE).
