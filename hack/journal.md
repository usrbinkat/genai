# GenAI Development Journal

This is a journal of the development journey porting the [docker-compose] based [docker/genai-stack] project onto Pulumi + Kubernetes.

This repository is a derivative of the [docker/genai-stack] project and will merge back into a fork of the original project once the port is complete.

All recognition and credit for the application code and services goes to the authors and contributors of the source [docker/genai-stack] project.

[docker/genai-stack]: https://github.com/docker/genai-stack
[docker-compose]: https://github.com/docker/compose

## usrbinkat <> 2024.02.10

1. Create a new repository on GitHub from the [github.com/pulumi/devcontainer](https://github.com/pulumi/devcontainer) template.
1. Clone the repository to my local machine.
1. Customize the `.devcontainer/devcontainer.json` file for this genai project.
1. Authenticate to Pulumi Cloud with `pulumi login` using a Pulumi Personal Access Token.
1. Initialize a new Pulumi ESC Environment named `genai`
1. Create a Pulumi ESC genai environment including:
   - GITHUB_USER
   - GITHUB_EMAIL
   - GITHUB_TOKEN

## usrbinkat <> Load Pulumi ESC Environment

```bash
eval $(esc open usrbinkat/genai --format shell)
```

## Port Docker image build artifacts

1. Relocate Dockerfiles to ./docker/$service directory
2. Relocate docker image build assets to root of project directory
3. Write a .dockerignore file to reduce build context overhead
