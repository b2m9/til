# Update email and author information in Git history

To update email and/or author information in Git, the `filter-branch` command can be used. [1]
The following script can be used to update email and author information:

```
$ git filter-branch --commit-filter '
    if [ "$GIT_AUTHOR_EMAIL" = "old@email.address" ];
    then
        GIT_AUTHOR_NAME="New Name";
        GIT_AUTHOR_EMAIL="new@email.address";
        git commit-tree "$@";
    else
        git commit-tree "$@";
    fi' HEAD
```

Github provides a sightly different version of the script, using `--env-filter`
instead of `--commit-filter`: [2]

```
git filter-branch --env-filter '

    OLD_EMAIL="your-old-email@example.com"
    CORRECT_NAME="Your Correct Name"
    CORRECT_EMAIL="your-correct-email@example.com"
    
    if [ "$GIT_COMMITTER_EMAIL" = "$OLD_EMAIL" ]
    then
        export GIT_COMMITTER_NAME="$CORRECT_NAME"
        export GIT_COMMITTER_EMAIL="$CORRECT_EMAIL"
    fi
    if [ "$GIT_AUTHOR_EMAIL" = "$OLD_EMAIL" ]
    then
        export GIT_AUTHOR_NAME="$CORRECT_NAME"
        export GIT_AUTHOR_EMAIL="$CORRECT_EMAIL"
    fi
    ' --tag-name-filter cat -- --branches --tags
```

References:

- [1] [Git Tools - Rewriting History](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History)
- [2] [Github: Changing Author Info](https://help.github.com/articles/changing-author-info/)
