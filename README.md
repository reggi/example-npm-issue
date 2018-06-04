# `example-npm-failure`

> `npm` version `6.1.0`

I have a monorepo here, I've stripped out the contents from each of the individual package, they don't seem to have any impact on the bug.

The issue is that I am trying to start with nothing installed, and only install one package at the root of the this repo.

I am simply running `npm i file:packages/dep-merge-cli` and I get this reproducable error:

```
➜  example-npm-failure git:(master) ✗ npm i file:packages/dep-merge-cli
npm WARN example-npm-failure@1.0.0 No description
npm WARN example-npm-failure@1.0.0 No repository field.

npm ERR! path /Users/thomas/Desktop/example-npm-failure/node_modules/.staging/lodash-207c2806
npm ERR! code ENOENT
npm ERR! errno -2
npm ERR! syscall rename
npm ERR! enoent ENOENT: no such file or directory, rename '/Users/thomas/Desktop/example-npm-failure/node_modules/.staging/lodash-207c2806' -> '/Users/thomas/Desktop/example-npm-failure/packages/journey.coerce-to-array/node_modules/lodash'
npm ERR! enoent This is related to npm not being able to find a file.
npm ERR! enoent

npm ERR! A complete log of this run can be found in:
npm ERR!     /Users/thomas/.npm/_logs/2018-06-04T04_00_30_039Z-debug.log
```

I did check and see that all of these modules use the **same** version of lodash, and the error is still happening.
