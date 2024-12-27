# webpack-template

Webpack development template repository for SPA-like front-end only apps that includes:

- A minimal project structure
- Webpack v5 configuration
- ESLint v9 configuration

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

### Webpack v5 Configuration

Webpack configuration following [their documentation](https://webpack.js.org/concepts/). Includes:

- 3 config files (common, dev, & prod), that are managed with webpack-merge package & npm scripts
- HTMLWebpack plugin to build from the template.html file (needs tuning for MPAs)
- Configured webpack dev server
- Various configured loaders to handle assets & styles
- Scripts to start dev server and build (see `package.json`)

### ESLint v9 Configuration

ESLint configuration following [their documentation](https://eslint.org/docs/latest/). Includes:

- A vanilla configuration in `eslint.config.mjs` (result of `npm init @eslint/config@latest)
- Scripts to lint and fix code over the /src directory



