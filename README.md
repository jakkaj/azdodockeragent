# Docker Build Agent for Azure Devops

This project allows you to set up a Docker based build agent on any machine quickly. 

It supports Docker in Docker builds. 

## Requirements

You must have Docker and `docker-compose` installed on your machine. If you're on Windows, then you must run this from WSL2. 

You will need to do some stuff in Azure DevOps - see the [instructions located here](https://docs.microsoft.com/en-us/azure/devops/pipelines/agents/docker?view=azure-devops).

## Getting Started

After cloning the repo you will need to set up some environment variables in the `.env` file. 

- Make a copy of `.env.template` and rename it to `.env`
- Fill in the fields. See [Run a self-hosted agent in Docker](https://docs.microsoft.com/en-us/azure/devops/pipelines/agents/docker?view=azure-devops#environment-variables) for more info


## Running

The agent is started using `docker-compose`. Run `./run.sh` to get started. 

By default it will run interactively so you can see stuff happening, if you want to run it in the background then edit `run.sh` and replace the line `docker-compose up` with `docker-compose up -d`

If you want the agent to run after restarts and things, edit `docker-compose.yaml` and uncomment the line `restart: always` before running `./run.sh` again. 

