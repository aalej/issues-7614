# Repro for issue 7614

## Versions

firebase-tools: v13.16.0<br>
platfrom: macOS

## Steps to reproduce

1. Run `firebase deploy`

## Notes

Using the template from https://github.com/bluwy/create-vite-extra/tree/master/template-ssr-react and following the steps from https://firebase.google.com/docs/hosting/frameworks/express, modified:

1. Added the ff to `template-ssr-react/package.json`

```json
  "directories": {
    "serve": "dist"
  },
  "files": [
    "dist",
    "server.js"
  ],
  "main": "server.js"
```

2. `template-ssr-react/server.js`
   - Replaced `app` with `server` then created a function called `app` to export the server

```js
export function app() {
  return server;
}
```
