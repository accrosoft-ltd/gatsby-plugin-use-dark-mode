# [gatsby-plugin-use-dark-mode][home]

[![npm version][npm-image]][npm-url]

A [Gatsby][gatsby] plugin to prevent a flash of default styles when using the
[`use-dark-mode`][udm] hook if the user is not using the default theme.
Specifically, this plugin handles the injection of the
[`noflash.js`][udm-noflash] logic.

## Install

```sh
yarn add gatsby-plugin-use-dark-mode use-dark-mode
```

## Usage

Add the plugin to your `gatsby-config.js`.

<!-- prettier-ignore -->
```js
module.exports = {
  plugins: [
    'gatsby-plugin-use-dark-mode',
  ],
};
```

Follow the [`use-dark-mode`][udm] documentation for further instructions.

### Advanced Configuration

If you would like to specify the class names used (which you will also be
passing to [`useDarkMode`][udm-parameters]) or skip the script minification
process, you may do so through plugin options:

```js
// gatsby-config.js
module.exports = {
  plugins: [
    {
      resolve: 'gatsby-plugin-use-dark-mode',
      options: {
        classNameDark: 'dark-mode',
        classNameLight: 'light-mode',
        minify: true,
      },
    },
  ],
};
```

## Limitations

[`useDarkMode`][udm] can be [configured][udm-parameters] to specify which DOM
element receives the class and to use an alternate storage provider if desired.
This plugin does not currently support those options, so it will only work if
you are using the defaults (`document.body` and `localStorage`).

[home]: https://github.com/wKovacs64/gatsby-plugin-use-dark-mode
[npm-image]:
  https://img.shields.io/npm/v/gatsby-plugin-use-dark-mode.svg?style=flat-square
[npm-url]: https://www.npmjs.com/package/gatsby-plugin-use-dark-mode
[gatsby]: https://www.gatsbyjs.org
[udm]: https://github.com/donavon/use-dark-mode#readme
[udm-noflash]: https://github.com/donavon/use-dark-mode#that-flash
[udm-parameters]: https://github.com/donavon/use-dark-mode#parameters
