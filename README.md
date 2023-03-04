Welcome! 

This is my test book using bookdown and renv. As a developer, these are your steps:
1. Make updates on your local version.
  - Ensure that packages are all included in the environment 
    - Now, when in this package, loading packages (for example, 'install.packages("<package>")') will call it as renv needs it ('renv::install("<package>")'). You can use either. Eventually you need to ensure it is in the lock file when submitting to github. This can be done with 'renv::snapshot()' to check all current libraries or you can look up more information on this package to just submit one library. You can also manually change the information in the lockfile ('renv.lock'). I also recommend use of 'renv:restore()' which loads all packages in the lockfile, ensuring you are not doing anything you haven't made available.
    - One caveat, be careful on only updating the libraries you need. Sometimes there are reasons to downgrade a package for the server (i.e. a version is not available to the github server), and so updating everything to the most current version can result in previously unencountered failures.
  - Check if things are locally working with 'bookdown::serve_book()'.
2. Push changes and with no problems, merge with dev. Ensure none the github actions don't fail and fix any issues. Actions will show if it will successfully publish, but will not publish it (only main is published). The merge with dev may happen locally or online depending on the guidelines determined.
4. Submit a PR for dev to main. Be sure to explain what it does and I also recommend specifying reviewers if possible. 


When approved and merged to main, actions will check and publish it. Note, it may take a few minutes, so don't worry if changes are not instantly displayed.
