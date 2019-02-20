# Docker_Implementation
Information about implementation code with docker

## Create a customized container
It is possible to create your own Dockerfile to create a customized SQL Server container. For more information, see a demo that combines SQL Server and a Node application. If you do create your own Dockerfile, be aware of the foreground process, because this process controls the life of the container. If it exits, the container will shutdown. 

**For example, if you want to run a script and start SQL Server, make sure that the SQL Server process is the right-most command). All other commForands are run in the background**. 

This is illustrated in the following command inside a Dockerfile:

```bash
/usr/src/app/do-my-sql-commands.sh & /opt/mssql/bin/sqlservr
```
If you reversed the commands in the previous example, the container would shutdown when the do-my-sql-commands.sh script completes.
