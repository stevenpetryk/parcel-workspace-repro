# Reproducing issue with Parcel + workspaces

## Setup

This repo has two packages, `app/` and `common/`. `app` is a Parcel app. `common` is just some TSX (doesn't get compiled).

```bash
cd app
yarn install
yarn start
```

Notice that Parcel seems to be parsing `common/utils.tsx` as if it's plain JS, despite the extension being TSX. It treats the JSX closing tag `/` as a regex.

## What I'd like to know/do

This repo is a really small simulation of Discord's frontend architecture. We also have uncompiled TSX code shared using yarn workspaces.

It would be excellent to know if it's possible to mark certain node_modules as things that Parcel needs to compile, as opposed to assuming it's just plain JS.
