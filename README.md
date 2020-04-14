# boilerplate-husky-lint-staged-prettier

:fork_and_knife: Setup code formatter as a pre-commit Git hooks task only for changed files

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
    "husky": {
        "hooks": {
            "pre-commit": "lint-staged"
        }
    }
    ...
    ```

4. Create config files by coping with this template:

    - [lint-staged.config.js]
    - [prettier.config.js]

[husky]: https://github.com/typicode/husky
[lint-staged]: https://github.com/okonet/lint-staged
[prettier]: https://github.com/prettier/prettier
[lint-staged.config.js]: https://github.com/piecioshka/boilerplate-husky-lint-staged-prettier/blob/master/lint-staged.config.js
[prettier.config.js]: https://github.com/piecioshka/boilerplate-husky-lint-staged-prettier/blob/master/prettier.config.js
