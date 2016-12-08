## Add `pre-commit` hook to your local `git`
1. Inside of your js project, go to `.git` directory
2. go to `hooks`.
3. `mv pre-commit.sample pre-commit`
4. delete all the content in `pre-commit` file and 
5. add the line `yarn run lint` to the `pre-commit` file
