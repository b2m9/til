# Push to multiple Git remote locations

A single remote for fetch and pull can be easily added via:

```
git remote add $remote-name $remote-location
```

An additional push location can be added:

```
git remote set-url --add --push $remote-name $remote-location
```

However, Git will replace the original push URL (it is the intended behaviour).
Therefore, the previous push URL needs to be added again with the same command.

The remotes can be verified:

```
git remote -v
```