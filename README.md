# update-gh-pages-branch-from-subdirectory-within-master-branch-with-git-subtree

update gh-pages branch from subdirectory within master branch with `$ git subtree`

## Example

```console
$ # in master branch
$ echo > README.md
$ git add .
$ git commit -m "added README.md"
$ git checkout --orphan gh-pages
$ # in gh-pages branch
$ git reset HEAD --
$ git clean -fdx
$ echo '<!DOCTYPE html>' > index.html
$ git add .
$ git commit -m "added index.html"
$ git checkout master
$ # in master branch
$ git subtree add --prefix docs origin gh-pages
$ cd docs && touch .nojekyll && cd ..
$ git add .
$ git commit -m "added .nojekyll"
$ git subtree push --prefix docs origin gh-pages --squash
```

## License

The MIT license.
