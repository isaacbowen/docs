# A future of AI code

Software modules exist as individual files, opening with a comment naming the file's path relative to the app's root directory, and similar comment lines identifying the files where any required modules are defined. Each individual file contains the module definition _and_ tests for it. Whenever the file is loaded, the caller runs the tests and uses the results to decide whether to load the module or raise an error.

I think that covers everything.
