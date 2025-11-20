
### Common useful Docker commands

Use these in a terminal where Docker is available.

Show running containers:

```bash
docker ps
```

Show all containers (running or stopped):

```bash
docker ps -a
```

Stop a running container (graceful):

```bash
docker stop ollama
docker stop open-webui
```

Force-stop immediately (if stop hangs):

```bash
docker kill ollama
docker kill open-webui
```

Start an existing stopped container:

```bash
docker start ollama
docker start open-webui
```

Restart (stop then start):

```bash
docker restart ollama
docker restart open-webui
```

Remove a container (only if you really want to delete it and its state):

```bash
docker rm ollama
docker rm open-webui
```

View logs (helpful for debugging):

```bash
docker logs -f ollama
docker logs -f open-webui
```

Run a shell inside a running container:

```bash
docker exec -it ollama /bin/bash   # or /bin/sh if bash not available
docker exec -it open-webui /bin/bash
```

# How to run them again (recreate from your file)

Your notes show these `docker run` commands — use them to create & run containers (they mount volumes and map ports):

Ollama:

```bash
docker run -d \
  -v ollama:/root/.ollama \
  -p 11434:11434 \
  --name ollama \
  ollama/ollama
```

Open WebUI:

```bash
docker run -d \
  -p 3000:8080 \
  -v open-webui:/app/backend/data \
  --name open-webui \
  ghcr.io/open-webui/open-webui:main
```

(or use `:main-slim` image if you prefer the slim variant).

# Quick checklist if “something is a mess”

1. `docker ps -a` — see status and container names.
    
2. If a container is **exited**, view logs: `docker logs <name>` to see errors.
    
3. If ports conflict (e.g., 3000 already used), either stop the process using the port or choose different host port (`-p 4000:8080`).
    
4. If you want a clean start: stop → remove → re-run the `docker run` commands above.
    
    ```bash
    docker stop open-webui ollama
    docker rm open-webui ollama
    # then re-run the docker run lines above
    ```
    
5. To see if web UIs are reachable:
    
    - OpenWebUI: visit `http://localhost:3000` (or whichever host port you mapped).
        
    - Ollama API: typically listens on `localhost:11434` (check docs / logs).
        

# Extra tips

- If you changed container names, replace `ollama` / `open-webui` in the commands with the names from `docker ps -a`.
    
- If containers crash right after start, `docker logs` will show the reason (missing model files, permission errors, port in use, etc.).
    
- If you want to preserve data, keep the `-v` volume mappings (those make data persistent between restarts).
    

---

If you paste the output of `docker ps -a` and `docker logs open-webui` (or `ollama`), I’ll read them and tell you exactly what’s failing and how to fix it.