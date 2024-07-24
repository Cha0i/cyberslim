# App documentation

## Git
Code lives on four places through git

- local `code on your machine`
- staging area `code ready to be added to commit`
- commit `collection of changes made to repo`
- repo `short for repository, the final code on github`

Connecting to repo
```
git remote add origin <link>
```

Checking changes staged for commit
```
git status
```

Adding changes to commit `adds all changed files to commit, you can also do file.sth instead of .`
```
git add .
```

Making a commit
```
git commit -m "What changed?"
```

Pushing commit to repo `pushes to main branch`
```
git push -u origin main
```