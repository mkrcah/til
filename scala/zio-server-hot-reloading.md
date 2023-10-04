## Zio server hot reloading

UPDATE: see [https://github.com/spray/sbt-revolver](sbt-revolver)

I was wondering about hot-reloading the local zio server
and ended up with the following setup, which seems to be working well:

1. fork the jvm for runs by setting `Compile / run / fork := true` in build.sbt, so that cmd+c also kills the server
   process (and frees the port)
2. start the server with `~run` to enable compilation and rerunning immediately after the cmd+c