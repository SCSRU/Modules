Welcome! 

This is my test book using bookdown and renv. As a developer, these are your steps:
1. Make updates on your local version.
  - Ensure that packages are all included in the environment (run 'renv::update("<package>")' or 'install("<package>")'. Updating all packages can be done with 'renv::snapshot()', however, if there was a package that needed to be downgraded for server reasons that is not on yours, you may run into problems.)
  - Check if things are working with `bookdown::serve_book()'
2. Push changes (ensure that the actions do not fail)
3. Merge with dev
4. PR to main

Upon approval to main PR, the github page will be updated and deployed. Note, the online update may take a few minutes after merge.