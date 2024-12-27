# webpack-template

Webpack development template repository for SPA-like front-end only apps that includes:

- A minimal project structure
- Webpack v5 configuration

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

Webpack configuration that includes:

- 3 files (common, dev, & prod), that are managed with webpack-merge package & npm scripts
- HTMLWebpack plugin to build from the template.html file (needs tuning for MPAs)
- Configured webpack dev server
- Various configured loaders to handle assets & styles



