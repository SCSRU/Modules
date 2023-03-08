Welcome! 

This is the test version of automating the SCCRU book publishing process.

As a developer, this repo can be used very similar to that done previously. However, since there are a few process changes, I have outlined the steps below.

0. Pull the project for github.
- I also recommend pulling the library enviroment in R to ensure a smoother transistion later. This is done with 'renv::restore()', which get the libraries and versions last used. This may be duplicative after pulling, but for now, not a bad practice. 
1. (As before) Write or edit a the modules using the .Rmd files. 
- I recommend using a new github branch for your changes for several reasons, but importantly, it will aid in knowing if your changes have any issues when publishing the book online.
- Be sure to include references in the 'references.bib' file as well as ensuring any new modules are noted in the '_bookdown.yml' file.
2. Include any necessary packages in the renv environment. 
- If the programming was done in the project, commands such as 'install.packages("<package>")' will call renv as needed, for example 'renv::install("<package>")'. 
- You also need to save the packages to the 'renv.lock' file. This is done with 'renv::snapshot()'. 
- I recommend only updating the packages you need as some packages are downgraded for github server reasons (when you run snapshot it will confirm if you want to upgrade the packages). Additionally, you can modify the lock file directly.
3. Compile and check the book changes work as desired.
- This is done locally such through commands like 'bookdown::serve_book()'.
- If a package was not included in renv, you will get an error that gives the file and location then states "Error in library(<package>) : there is no package called '<package>' "
4. Push changes.
- Github actions will check if there are any issues. You can look at the changes directly on that tab, or create a PR to merge branch with dev. In both cases, no changes will result in a check and a failure in an x. 
  - If the error is a missing package (i.e. not in renv) you will get an error in 'Build site' step saying "Error in library(<package>) : there is no package called '<package>' ". 
  - Another possible error in the 'Run r-lib/actions/setup-renv@v2' step. It generally says something like "Error: failed to retrieve package '<package>@<version>' ". This generally means the server cannot locate the package. Downgrading the package version is often the simpliest solution.
- Merge with dev once the issues are clean. Note this will not change the published book.
5. Submit a PR for dev to main. 
- In the real case, this will require approval from some specified number of people, but for now, this feature is disabled so you can practice.
- Once dev is merged to main, github actions will check and publish. You can verify the progress in the actions page. After completion, if you go to the website and don't notice changes, be sure to refresh the page.

