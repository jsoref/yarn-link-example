# sample yarn link package

## Baseline

```sh
yarn install
```

## Test

```sh
yarn-link-example % yarn test
yarn run v1.22.19
$ node ./index.js
1
✨  Done in 0.15s.
```

## Set up replacement dependency

```sh
yarn-link-example % cd ..; gh repo clone jsoref/smallest >/dev/null 2>/dev/null; cd smallest
smallest % yarn link
yarn link v1.22.19
success Registered "smallest".
info You can now run `yarn link "smallest"` in the projects where you want to use this package and it will be used instead.
✨  Done in 0.02s.
```

## Use replacement

```sh
smallest % cd ../yarn-link-example
yarn-link-example % yarn link smallest
yarn link v1.22.19
success Using linked package for "smallest".
✨  Done in 0.03s.
yarn-link-example % yarn test
yarn run v1.22.19
$ node ./index.js
smallest 1
1
✨  Done in 0.28s.
```
