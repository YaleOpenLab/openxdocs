# Integration tests

The platform has unit tests for different modules but there are no integration tests which can test functionality that requires intervention and user interaction. Integration tests help test the end-end flow of the platform, and changes to code that affect this flow can be easily identified. Integration tests also help catch edge cases and help prevent breaking changes from being merged into the codebase.

Integration tests need not be restricted to Golang, they can be in Python or other languages too. Tests need to be run on Travis CI so new Pull Requests to the repo can be thoroughly tested before being merged into the codebase.

