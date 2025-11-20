**Ollama** — a local LLM runtime / model host that lets you run large language models on your machine and serve them via a local API.  
**OpenWebUI** — a browser-based front-end (web UI) that lets you interact with models (chat, settings, files) — often used to talk to locally hosted models.

1. Pull the Ollama image

```
docker pull ollama/ollama
```

2. Create ollama container
	* Note you skip step 1 because check before create the contain if the image is available or not if not available pull the image then create the container
```
docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama
```

3. Pull the Open WebUI Image

```
docker pull ghcr.io/open-webui/open-webui:main
```

4. Run the Container

```
docker run -d -p 3000:8080 -v open-webui:/app/backend/data --name open-webui ghcr.io/open-webui/open-webui:main
```

To use the slim variant instead:

```
docker run -d -p 3000:8080 -v open-webui:/app/backend/data --name open-webui ghcr.io/open-webui/open-webui:main-slim
```

#### Important Flags

- **Volume Mapping (`-v open-webui:/app/backend/data`)**: Ensures persistent storage of your data. This prevents data loss between container restarts.
- **Port Mapping (`-p 3000:8080`)**: Exposes the WebUI on port 3000 of your local machine.

5. To see if web UIs are reachable:
    
    - OpenWebUI: visit `http://localhost:3000` (or whichever host port you mapped).
        
    - Ollama API: typically listens on `localhost:11434` (check docs / logs).

FOR information
* [Ollama docker image](https://hub.docker.com/r/ollama/ollama)
- [Open WebUI Documentation quick start](https://docs.openwebui.com/getting-started/quick-start/)
- [Available models on Ollama](https://ollama.com/search)
