# sv

Everything you need to build a Svelte project, powered by [`sv`](https://github.com/sveltejs/cli).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```sh
# create a new project
npx sv create my-app
```

To recreate this project with the same configuration:

```sh
# recreate this project
pnpm dlx sv@0.15.3 create --template minimal --types ts --install pnpm ux
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```sh
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```sh
npm run build
```

You can preview the production build with `npm run preview`.

## Deploying to Cloudflare Pages

This project is configured for Cloudflare Pages with `@sveltejs/adapter-cloudflare`.

Use these settings when connecting the repository in Cloudflare Pages:

```sh
Build command: pnpm run build
Build output directory: .svelte-kit/cloudflare
```

The same output directory is also declared in `wrangler.toml` with `pages_build_output_dir`.
