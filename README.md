# genAI-business-assistant
Local env to run cheshire cat + business assistant 

Setup

1. Add submodules

```
git submodule update --init --recursive
```

2. Setup up local cat
    1. cd `cd local-cat`
    1. Build the cat: `docker-compose up`
        - if the build fails because you are not using an NVIDIA GPU comment this part of `docker-compose.yml`
            ``````
            # environment:
            #   - gpus=all
                # deploy:
                #   resources:
                #     reservations:
                #       devices:
                #         - driver: nvidia
                #           count: 1
                #           capabilities: [gpu]
            ``````
    1. Pull the desired model from ollama library: `docker exec ollama_cat ollama pull <model_name:tags>`
    Here you can select the model you want from [Ollama model library](https://ollama.ai/library)

3. Move the local cat plugin in the folder `local-cat/cat/plugins`