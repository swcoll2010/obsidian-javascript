The package.json file contains the meta for the project, the npm run commands and the packages for the projects dependencies and development dependencies.

For the packages installed there is usually a version number.

  "dependencies": {
    "express": "^4.18.2",
    "typescript": "^4.9.3"
  },
  "devDependencies": {
    "jest": "^29.3.1"
  }

The first number is the major verision number. Going from major version to another may introduce breaking changes, the npm outdated command [[NPM Commands]], shows which packages are outdated.

The second number is the minor version, and it's usually safe to update as this shouldn't break the application.

The third  number is the patch version, this definitely shouldn't break the package and it should be safe to update the package.

You will see the the following table items listed when running the npm outdated command:

* package name
* current package version
* wanted package version
* lastest package version
* location

The listing is coloured, so that:

* yellow, means that there are major updates that won't be applied by npm update
* red means that there are minor/pactch version that can be updated
* no listing means that there are no out of date

The npm update command will update the packages, however, this is controlled by the modifying character before the version, there can be a number of characters:

* ^ : this is the default and will update only the minor and patch versions, major version updates are not allowed
* ~ : restrict updates to the patch version only
* * : except all updates including major updates which may break code
* no character, this pegs the package at that particular version

The star replaces the version type number, i.e. 1.0.2 could have \*.0.2 the star replaces the major version number.

The [[package-lock.json]] file contains each installed packages dependencies, and is used during the npm install command to ensure that the project maintains consistency.

How are seperate package dependencies handled?

## Major version package update

You'll need to run the install command again

	npm install <packagename>@latest



