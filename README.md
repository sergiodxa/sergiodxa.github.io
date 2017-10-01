# Personal site
This is the code behind `sergio.now.sh`.

## Stack
- Next.js
- React
- Now.sh

## How to run
### Development
All that's needed to run this blog is:

```bash
yarn
yarn dev
```

Then head to http://localhost:3000. Changes you make to components will henceforth be reflected there in realtime.

### Deployment

All that's needed to deploy this site to the cloud is to execute a single command

```
yarn deploy
```

This will build and export to HTML files the site, deploy it to [Now.sh](https://now.sh) and then alias it automatically.

## Scripts
- `dev` -> run the development server
- `build` -> build Next.js for production
  - `preexport` -> run `build`
- `export` -> export Next.js as a static site
  - `postexport` -> copy the service worker and run `build:rss`
- `build:rss` -> generate the atom feed file
- `alias` -> alias the latest deployment
- `clean` -> remove old unaliased deployments
  - `prestart` -> run `export`
- `start` -> serve the statically exported site
  - `predeploy` -> run `export`
- `deploy` -> deploy to Now the statically exported site
  - `postdeploy` -> run `alias` and run `clean`
- `set:rules` -> set the rules.json aliases for `sergio.now.sh`
