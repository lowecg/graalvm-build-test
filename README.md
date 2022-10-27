
Repro for https://github.com/oracle/graal/issues/5303

Prerequisites:

You’ll need Docker running and [Babashka](https://github.com/babashka/babashka) installed.

See `bb.edn` line 54 for GraalVM native build options applied:

```clojure
   :native-image-args ["--verbose"
                       "--no-fallback"
                       "--report-unsupported-elements-at-runtime"
                       "-H:+AllowIncompleteClasspath"
                       "--no-server"
                       "--enable-monitoring=heapdump"]}}
```

This project currently results in the native build crash on GraalVM 22.3 CE:

```
bb hl:compile && bb hl:native:executable
```


The project is based on holy-lambda. Documentation is available [here](https://fierycod.github.io/holy-lambda).

