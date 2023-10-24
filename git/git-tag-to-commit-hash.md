## Translating git tag to git commit hash

You can go from a git tag to a git commit hash using `git rev-parse`:

```shell
$ git rev-parse some-tag
0167978e939526def4f5751c20edf3ede3ca5259
```

Further reading:
- https://stackoverflow.com/questions/15798862/what-does-git-rev-parse-do