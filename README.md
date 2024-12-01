# boilerplate-husky-lint-staged-prettier

🍴 Setup code formatter as a pre-commit Git hooks task only for changes

## Goals

- 🐶 Use [husky](https://typicode.github.io/husky/) to set `pre-commit` hooks
- 🧱 Use [lint-staged](https://github.com/lint-staged/lint-staged) to process only changes in files (not whole project)
- 🧬 Use [prettier](https://github.com/prettier/prettier) to have the consistent syntax in all files

## How to setup them in my project? 🎉

1. Create `package.json`:

   ```json
   {
     "name": "boilerplate-husky-lint-staged-prettier"
   }
   ```

2. Install deps:

   ```bash
   npm install -D prettier lint-staged husky
   ```

3. Update `package.json` and add: scripts, lint-staged and prettier configuration:

   ```json
   {
     "name": "boilerplate-husky-lint-staged-prettier",
     "scripts": {
       "prepare": "husky",
       "pre-commit": "lint-staged"
     },
     "lint-staged": {
       "*.md": "prettier --write"
     },
     "prettier": {
       "arrowParens": "always",
       "bracketSameLine": false,
       "bracketSpacing": true,
       "embeddedLanguageFormatting": "auto",
       "endOfLine": "lf",
       "htmlWhitespaceSensitivity": "css",
       "insertPragma": false,
       "jsxSingleQuote": false,
       "printWidth": 80,
       "proseWrap": "preserve",
       "quoteProps": "as-needed",
       "requirePragma": false,
       "semi": true,
       "singleAttributePerLine": false,
       "singleQuote": false,
       "tabWidth": 2,
       "trailingComma": "all",
       "useTabs": false,
       "vueIndentScriptAndStyle": false
     }
   }
   ```

4. Make a Git commit 🎊

## License

[The MIT License](https://piecioshka.mit-license.org) @ 2020
