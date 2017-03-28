# List all globally installed NPM packages

Recently I have wondered how to list all globally installed NPM packages and 
what version they are. Turned out, I had to ask Google for it. [1]

```shell
npm list -g --depth=0
```

Important is the parametre `depth`. It specifies how deep `npm list` will show
the installed packages and their dependencies. Therefore, `--depth=0` only shows
the top level.

References:
- [1] [PonderingDeveloper.com](https://ponderingdeveloper.com/2013/09/03/listing-globally-installed-npm-packages-and-version/)
