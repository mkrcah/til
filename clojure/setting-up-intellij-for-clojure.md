## Setting up Intellij for Clojure

Intellij IDEA has been my go-to IDE and I have been wondering 
how to set it up for Clojure development. Here are some tips:

- Cursive plugins seems to be a popular path. It seems to be actively developed, as of 2023.
- When adding a project, Intellij might not recognize some symbols or fail to start the main function. To fix that, ensure Leiningen's `project.clj` is added as a project. (`project.clj` is like setting up a sbt Scala project with `build.sbt`)
- REPL might be inactive at first. REPL is attached to `project.clj` project file, so one needs to initialize the REPL from there, see [here](https://cursive-ide.com/userguide/first-repl.html)
  - To make a new dependency work in REPL, you need to restart the REPL.     
- Editing might be surprising, the paredit is turned on by default. Check [the structural editing doc](https://cursive-ide.com/userguide/paredit.html). 