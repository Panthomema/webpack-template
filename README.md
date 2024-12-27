# webpack-template

Webpack development template repository for SPA-like front-end only apps that includes:

- A minimal project structure
- Webpack v5 config
- ESLint v9 config
- StyleLint v16 config

## Details

### Project Structure

Following webpack standards:

project/
- src/
  - assets/
  - styles/
    - reset.css
  - index.js
  - template.html
- dist/
  - ...(webpack build output)
- ...(config files)

### Webpack v5 Config

Webpack configuration following [their documentation](https://webpack.js.org/concepts/). Includes:

- 3 config files (common, dev, & prod), that are managed with webpack-merge package & npm scripts
- HTMLWebpack plugin to build from the template.html file (needs tuning for MPAs)
- Configured webpack dev server
- Various configured loaders to handle assets & styles
- Scripts to start dev server and build (see `package.json`)

### ESLint v9 Config

ESLint configuration following [their documentation](https://eslint.org/docs/latest/). Includes:

- A vanilla configuration in `eslint.config.mjs` (result of `npm init @eslint/config@latest`)
- Scripts to lint and fix code over the /src directory
- If you want to lint JS code inside `<script>` tags, check [eslint-plugin-html](https://www.npmjs.com/package/eslint-plugin-html)

### StyleLint v16 Config

Stylelint configuration following [their documentation](https://stylelint.io/). Includes:

- A vanilla configuration in `stylelint.config.mjs` (result of `npm init stylelint`, replaced `eslintrc.json`)
- Scripts to lint and fix code over the /src/styles directory
- If you want to lint CSS code inside `<style>` tags, check [stylelint-config-html](https://www.npmjs.com/package/stylelint-config-html) - and unset the `html` value set in cofig file `ignoreFiles` option (it is set to prevent VSCode StyleLint extension screaming)



