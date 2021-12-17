## Setup
We configure anonymous access to a custom domain for GitHub Maven Packages by
 - redirecting all requests to `https://maven.packages.aklivity.io/...` to `https://maven.pkg.github.com/aklivity/packages/...`,
 - creating a machine account [PAT](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) outside the `aklivity` organization with `read:packages` scope only
 - injecting the machine account PAT in the redirected URL to support anonymous access

Thanks to [redirect.pizza](https://redirect.pizza/) for the assist!

## Verify

Verify anonymous read access to dependencies located in GitHub Packages.

```
./mvnw dependency:resolve
```

```
[INFO] Scanning for projects...
[INFO] 
[INFO] --------------------< io.aklivity.sandbox:toystore >--------------------
[INFO] Building toystore develop-SNAPSHOT
[INFO] --------------------------------[ jar ]---------------------------------
Downloading from anonymous: https://maven.packages.aklivity.io/io/aklivity/sandbox/toys/0.3/toys-0.3.pom
Downloaded from anonymous: https://maven.packages.aklivity.io/io/aklivity/sandbox/toys/0.3/toys-0.3.pom (550 B at 348 B/s)
Downloading from anonymous: https://maven.packages.aklivity.io/io/aklivity/sandbox/parent/0.3/parent-0.3.pom
Downloaded from anonymous: https://maven.packages.aklivity.io/io/aklivity/sandbox/parent/0.3/parent-0.3.pom (1.8 kB at 1.9 kB/s)
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
