# boilerplate-husky-lint-staged-prettier

:fork_and_knife: Setup code formatter as a pre-commit Git hooks task only for changes

## Goals

-   🐶 Use [husky] to set `pre-commit` hooks
-   🧱 Use [lint-staged] to process only changes in files (not whole project)
-   🧬 Use [prettier] to have the same syntax in the whole project

## How to setup in my project? 🎉

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

3. Insert in `package.json`:

    ```json
    ...
    "scripts": {
        ...
        "prepare": "husky install",
        "pre-commit": "lint-staged"
    },
    "lint-staged": {
        "*.md": "prettier --write"
    },
    "prettier": {
        "trailingComma": "all",
        "tabWidth": 2,
        "semi": true,
        "singleQuote": true,
        "arrowParens": "always",
        "proseWrap": "never"
    }
    ...
    ```

    Alternate option will be create files for each configuration:

    - [lint-staged.config.js](https://github.com/okonet/lint-staged#filtering-files)
    - [prettier.config.js](https://prettier.io/docs/en/configuration.html)

4. Husky

    Husky was evolved and introduce new way to setup Git hooks.

    - In this article, you can read about dropping `husky.config.js` file:
        - <https://blog.typicode.com/husky-git-hooks-javascript-config/>
    - There is a project to reduce overhead to setup Husky
        - <https://www.npmjs.com/package/husky-init>

    ```bash
    npx husky-init && npm install
    npx husky add .husky/pre-commit "npm run pre-commit"
    ```

5. Make a commit (using Git of course) and see how changed files look like 🎊

[husky]: https://typicode.github.io/husky/
[lint-staged]: https://github.com/okonet/lint-staged
[prettier]: https://github.com/prettier/prettier
[lint-staged.config.js]: https://github.com/piecioshka/boilerplate-husky-lint-staged-prettier/blob/master/lint-staged.config.js
[prettier.config.js]: https://github.com/piecioshka/boilerplate-husky-lint-staged-prettier/blob/master/prettier.config.js
