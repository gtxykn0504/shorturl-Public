# vercel-shorturl starter

Template for [vercel-shorturl](https://github.com/ThewApp/vercel-shorturl)

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/git/external?repository-url=https%3A%2F%2Fgithub.com%2FThewApp%2Fvercel-shorturl-starter&demo-title=vercel-shorturl&demo-description=Create%20your%20own%20shorturl%20on%20Vercel&demo-url=https%3A%2F%2Fvercel-shorturl-starter.vercel.app%2F)

## Demo

[Demo](https://vercel-shorturl-starter.vercel.app) is deployed with the example [redirects.yml](redirects.yml).

## Usage

1. [Create a new repository](https://github.com/ThewApp/vercel-shorturl-starter/generate) from this template.
1. Edit `redirects.yml`.
1. You **don't** need to edit `middleware.js`, install dependencies, or run `build` command.
1. Deploy to Vercel with `vc` command.

### Files

- `middleware.js` is required before deploying to Vercel. Do not delete it.
- `redirects.yml` is the main file for configuring shorturls. You can edit it to add more shorturls.
- `package.json` and `package-lock.json` are required before deploying to Vercel. Do not delete it.
- All files in `.gitignore` can be safely deleted.

## Features

For more features please visits [vercel-shorturl](https://github.com/ThewApp/vercel-shorturl#features).

---
- from: /me
  to: https://github.com/ThewBear
  status: 308 # Change status code ex. 301, 302, 307 (Default), 308
- from: /google/:q # Match exactly one ex. /google/recursion
  to: https://google.com/search?q=:q
- from: /vercel/:slug* # Match zero or more ex. /vercel /vercel/docs /vercel/solutions/nextjs
  to: https://vercel.com/:slug
- from: /twitter/:slug? # Match Zero or one ex. /twitter /twitter/thewdhanat
  to: https://twitter.com/:slug
- from: /github/:slug+ # One or more ex. /github/ThewApp github/ThewApp/vercel-shorturl
  to: https://github.com/:slug
- from: /dev/:slug1/:slug2 # Multiple match ex. /dev/p/information
  to: https://dev.to/:slug1/:slug2
- from: /google
  to: https://google.com/search?q=:q
  query:
    action: search # Must have this exact query
    q: :q # And this match in query ex. /google?action=search&q=recursion
- from: /dev
  to: https://dev.to/:user
  query:
    u: :user? # Optional match ex. /dev /dev?u=thewbear
