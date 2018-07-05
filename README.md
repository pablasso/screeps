# Screeps Game

This is my code for [Screeps](https://screeps.com/), an MMO RTS game for programmers where "the core mechanic is programming your units’ AI. You control your colony by writing JavaScript which operate 24/7 in the single persistent real-time world filled by other players on par with you".

## Setup

I'm using TypeScript with [screeds-typescript-starter](https://screepers.gitbooks.io/screeps-typescript-starter/) for the transpiler and deployment setups.

You will need:

 - NodeJS 9.5.0
 - NPM
 - Rollup CLI (install via `npm install -g rollup`)

To install run `npm install`.

The TypeScript source code is under `/src`.

Your screeps settings, including the key for deployments, goes into `screeps.json` which is not pushed on this repo. For an example configuration look at `screeps.sample.json`.

### Rollup and code upload

Running `rollup -c` will compile your code and do a "dry run", preparing the code for upload but not actually pushing it. Running `rollup -c --environment DEST:main` will compile your code, and then upload it to a screeps server using the `main` config from `screeps.json`.

You can use `-cw` instead of `-c` to automatically re-run when your source code changes - for example, `rollup -cw --environment DEST:main` will automatically upload your code to the `main` configuration every time your code is changed.

Finally, there are also NPM scripts that serve as aliases for these commands in `package.json` for IDE integration. Running `npm run push-main` is equivalent to `rollup -c --environment DEST:main`, and `npm run watch-sim` is equivalent to `rollup -cw --dest sim`.
