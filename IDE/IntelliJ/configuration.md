# Intellij configuration

## Configure wildfly remote debug

```txt
On Intellij
Run > Edit Configuration > + > Remote

Fill the  form with the specific host/port values (ex localhost/8787)

Copy the Command line argument for remote JVM
-agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=8787

On wildfly
Wildfly -> bin -> standalone.conf.bat

Uncomment the line
set "JAVA_OPTS=%JAVA_OPTS% -agentlib:jdwp=transport=dt_shmem,address=jboss,server=y,suspend=n"

Change the line configuration with the one created by IntelliJ
set "JAVA_OPTS=%JAVA_OPTS% -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=8787"
```

## Increment console buffer

```txt
CTRL + SHIFT + A
Registry
terminal.buffer.max.lines.count
```
