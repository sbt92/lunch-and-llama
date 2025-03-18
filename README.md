# Lunch and Llama

Lunch and Llama is a workshop that provides you with the necessary tools to get started with running and using Local Large Language Models on your workstation.

## Prerequisites

You will need a container runtime to complete this workshop. This has been tested on Docker. To get the Ollama stack running, execute the following commands:

```bash
docker compose pull
docker compose up -d
```

## Key Ollama Commands

To download a model:

```bash
docker exec -it ollama ollama pull <model_name>:<number_of_parameters>
```

To list the models on your workstation:

```bash
docker exec -it ollama ollama ls
```

To list running models on your workstation:

```bash
docker exec -it ollama ollama ps
```

To run a model in the terminal:

```bash
docker exec -it ollama ollama run <model_name>:<number_of_parameters>
```
for example:
```bash
docker exec -it ollama ollama run gemma3:1b
```

To delete a model:

```bash
docker exec -it ollama ollama rm <model_name>:<number_of_parameters>
```
for example:
```bash
docker exec -it ollama ollama rm gemma3:1b
```

## Demo Models We Used

To get the models we used in the workshop, run the following commands:

**Model for coding:**

```bash
docker exec -it ollama ollama run qwen2.5-coder:7b
```

**General purpose model:**

```bash
docker exec -it ollama ollama run llama3.1:8b
```

**Reasoning model:**

```bash
docker exec -it ollama ollama run deepseek-r1:14b
```

These are just some example models; you can find a wider selection on the [Ollama models page](https://ollama.com/search).

## Open WebUI

If you want an experience closer to ChatGPT or Gemini in your web browser, you can use OpenWebUI by visiting [http://localhost:8080](http://localhost:8080).

