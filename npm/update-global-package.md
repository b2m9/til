# Update globally installed NPM packages

To update a global package: `npm update -g $package`. To update all globally
installed packages, simply omit the `$package` name. [1]

To find out which packages are outdated, without updating them:
`npm outdated -g --depth=0`. 

References:
- [1] [docs.npmjs.org](https://docs.npmjs.com/getting-started/updating-global-packages)
