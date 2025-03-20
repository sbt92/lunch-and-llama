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

## Example Prompts We Used

### Initial test
We used the [gemma3:1b](https://ollama.com/library/gemma3:1b) model for this prompt:
```
Can you generate a welcome paragraph to the Lunch and Llama workshop.
```

### Generate Code

We used the [qwen2.5-coder:7b](https://ollama.com/library/qwen2.5-coder:7b) model for this prompt:

```plaintext
You are an excellent Python developer. Write a Python script to run the equivalent of this command: curl http://localhost:11434/api/show -d '{ "model": "qwen2.5-coder:7b" }'
```

```plaintext
Can you make the JSON output more readable in the terminal?
```

### Generate Text: Cover Letter for a Job Application

We used the [llama3.1:8b](https://ollama.com/library/llama3.1:8b) model for this prompt:

```plaintext
Generate me a cover letter for a job application for the Lead Cloud Engineer position at the company ACME Computers. Please ensure you capture:
- My AWS DevOps professional certification
- My latest project where I saved the company £150k by migrating their workload to the Cloud
- The mentorship scheme I set up to upskill Junior Cloud Engineers
```

```plaintext
I already work at ACME Computers, so let's make it slightly less formal. The hiring manager's name is Dave.
```

### Generate Text Using a Reasoning Model

We used the [deepseek-r1:14b](https://ollama.com/library/deepseek-r1:14b) model for this prompt:

```plaintext
My friend wants to plan a surprise birthday party for their partner who loves hiking and Italian food. They want to have the party on a Saturday afternoon in late spring near Bristol, UK. Suggest a possible itinerary for the day, including a scenic hike and a delicious Italian meal. Be specific with locations and timings, and explain your reasoning for each step.
```