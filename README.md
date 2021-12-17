# toystore

Verifies anonymous read access to dependencies located in GitHub Packages.

```
% ./mvnw dependency resolve

[INFO] Scanning for projects...
[INFO] 
[INFO] --------------------< io.aklivity.sandbox:toystore >--------------------
[INFO] Building toystore develop-SNAPSHOT
[INFO] --------------------------------[ jar ]---------------------------------
Downloading from anonymous: https://maven.packages.aklivity.io/io/aklivity/sandbox/toys/0.3/toys-0.3.pom
Downloaded from anonymous: https://maven.packages.aklivity.io/io/aklivity/sandbox/toys/0.3/toys-0.3.pom (550 B at 294 B/s)
Downloading from anonymous: https://maven.packages.aklivity.io/io/aklivity/sandbox/toys/0.3/toys-0.3.jar
Downloaded from anonymous: https://maven.packages.aklivity.io/io/aklivity/sandbox/toys/0.3/toys-0.3.jar (1.5 kB at 1.4 kB/s)
[INFO] 
[INFO] --- maven-dependency-plugin:2.8:resolve (default-cli) @ toystore ---
[INFO] 
[INFO] The following files have been resolved:
[INFO]    io.aklivity.sandbox:toys:jar:0.3:compile
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
```
