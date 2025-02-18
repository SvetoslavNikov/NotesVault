```powershell
docker ps
// process status - show the current containers
docker ps -a
// all containers stoppped ones too
docker ps -q
//IDs
docker ps --filter "ancestor=nginx"
//containers using specific img
```

```powershell
docker run -d -p 8080:80 --name my-first-container docker/getting-started

//first container created at lopcalhost 8080
```
