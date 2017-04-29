# Check if a node script was required
When you would like to determine if your node script was called from the command line, or if it was
included using a `require`.

Each nodejs module provides access to information for the current object via the `module` global. The filename property
on the module object specifies the entry point of the current application.

`require.main` is set to the `module` object when a file is run from nodejs, comparing the 2 objects allows us to check if a module
was called via a require statement.

`if (require.main === module) {
  // this module was called directly ie node foo.js...
}
else {
  // this module was required ie const m = require('some-module')
}`

## Links
* [Modules accessing the main module](https://nodejs.org/docs/latest/api/all.html#modules_accessing_the_main_module)
