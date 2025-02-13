# webpack-template

Webpack development template repository for SPA-like front-end only apps that includes:

- A minimal project structure
- Webpack v5 config
- ESLint v9 config
- StyleLint v16 config
- Prettier v3 config
- Workspace considerations

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

- A vanilla configuration in `stylelint.config.mjs` (result of `npm init stylelint`, replaced `stylelintrc.json`)
- Scripts to lint and fix code over the /src/styles directory
- If you want to lint CSS code inside `<style>` tags, check [stylelint-config-html](https://www.npmjs.com/package/stylelint-config-html) - and unset the `html` value set in cofig file `ignoreFiles` option (it is set to prevent VSCode StyleLint extension screaming)

### Prettier v3 Config

Prettier configuration following [their documentation](https://prettier.io/docs/en/). Includes:

- A minimal configuration in `prettier.config.mjs`, that adds some rules to the Prettier defaults
- A `.prettierignore` file, to avoid formatting some project parts
- Scripts to check and fix code over the /src directory

### Workspace Considerations

You should be able to work with this template in any code editor, running the npm scripts it provides in the CLI. By the way, to streamline the process, i recommend using it in VSCode with this extensions:

- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [StyleLint](https://marketplace.visualstudio.com/items?itemName=stylelint.vscode-stylelint)
- [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens)
- [Format Code Action](https://marketplace.visualstudio.com/items?itemName=rohit-gohri.format-code-action)

Add this to your user settings or your projects settings (experiment with them):

```
"editor.defaultFormatter": "esbenp.prettier-vscode",
"eslint.probe": ["javascript", "javascriptreact", "vue"],
"editor.formatOnSave": false, // Needs to be disabled to use codeActionsOnSave
"editor.codeActionsOnSave": [
  // Runs Prettier, then ESLint
  "source.formatDocument",
  "source.organizeImports",
  "source.fixAll.eslint"
],
"stylelint.validate": ["css", "html", "astro"],
"[css]": {
    "editor.codeActionsOnSave": [
      // Runs Prettier, then StyleLint
      "source.formatDocument",
      "source.organizeImports",
      "source.fixAll.stylelint"
    ]
  },
```
