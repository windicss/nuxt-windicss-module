![nuxt-windicss-module](https://repository-images.githubusercontent.com/343991410/68f83b80-811f-11eb-9638-51aed75785c4)

<h1 align='center'>nuxt-windicss-module</h1>

<p align='center'><a href="https://github.com/voorjaar/windicss">Windi CSS</a> for Nuxt.js, it's fast! ⚡️<br>
<sup><em>a.k.a On-demand Tailwind CSS</em></sup>
</p>

<p align='center'>
<a href='https://www.npmjs.com/package/windicss-webpack-plugin'>
<img src='https://img.shields.io/npm/v/windicss-webpack-plugin?color=0EA5E9&label='>
</a>
</p>

<p align='center'>
<a href='https://twitter.com/antfu7/status/1361398324587163648'>⚡️ See speed comparison with Tailwind</a>
</p>

## Features

- ⚡️ **It's FAST** - 20~100x times faster than [@nuxtjs/tailwindcss](https://github.com/nuxt-community/tailwindcss-module)
- 🧩 On-demand CSS utilities (Compatible with Tailwind CSS v2)
- 📦 On-demand native elements style reseting
- 🔥 Hot module replacement (HMR)
- 🍃 Load configurations from `tailwind.config.js`
- 📄 CSS `@apply` / `@screen` directives transforms (also works for Vue SFC's `<style>`)
- 🎳 Support Utility Groups - e.g. `bg-gray-200 hover:(bg-gray-100 text-red-300)`

## Install

```bash
yarn add nuxt-windicss-module -D
# npm inuxt-windicss-module -D
```

## Usage

Within your `nuxt.config.js` add the following.

```js
// nuxt.config.js
buildModules: [
  'nuxt-windicss-module',
],
```

This module won't work with `@nuxtjs/tailwindcss`, you will need to remove it.

```diff
buildModules: [
-  '@nuxtjs/tailwindcss',
],
```

This module will read from your root `tailwind.config.js` or `windi.config.js` config if present. See [here](https://windicss.netlify.app/guide/configuration.html) for details.


## Migrating

If you were previously using `@nuxtjs/tailwindcss`, please consult the [documentation](https://windicss.netlify.app/guide/migration.html) on migrating.

## Configuration

This module will resolve the option key with either `windicss` or `tailwindcss`.

`viewer`

- Default: `true`
- Development only

The module internally use [tailwind-config-viewer](https://github.com/rogden/tailwind-config-viewer) to setup the `/_windicss/` route.

To disable the viewer in development, set it to false:

```js
export default {
  windicss: {
    viewer: false
  }
}
```

`windicssOptions`
- Default:

```js
  scan: {
    dirs: ['./'],
    exclude: ['.nuxt/**/*']
  }
```  

- See [options.ts](https://github.com/windicss/vite-plugin-windicss/blob/main/packages/plugin-utils/src/options.ts) for configuration reference.


## Caveats

### Scoped Style

You will need to set `transformCSS: 'pre'` to get it work.

`@media` directive with scoped style can **only works** with `css` `postcss` `scss` but not `sass`, `less` nor `stylus`

## Credits

- Windy team
- [@antfu](https://github.com/antfu) Based on his Rollup / Vite implementation & his util package


## License

MIT License © 2021 [Harlan Wilton](https://github.com/loonpwn)

