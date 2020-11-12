# Docker Cheat Sheet
Docker Cheat Sheet for the most needed stuff..


<br><br>

# Pull
- Download OS from Docker rep
```bash
docker pull ubuntu
```

<br><br>

# Run
Create Docker Container with Ubuntu
```bash
docker run -d -t --name samplename ubuntu
```

<br><br>

# Ps
Show running Container
```bash
docker ps
```

<br><br>

# Exec
Enter bash of Container
```bash
docker exec -it samplename bash
```

<br><br>

# Exit
Exit container
```bash
exit
```
