# GitHubActionsRunnerContainer
[![GitHub Workflow Status (branch)](https://img.shields.io/github/workflow/status/hikarin522/GitHubActionsRunnerContainer/Build/master)](https://github.com/hikarin522/GitHubActionsRunnerContainer/actions/workflows/build.yml)
[![Docker Pulls](https://img.shields.io/docker/pulls/hikarin/github-actions-runner)](https://hub.docker.com/r/hikarin/github-actions-runner)
[![GitHub](https://img.shields.io/github/license/hikarin522/GitHubActionsRunnerContainer)](./LICENSE)

A docker container image of GitHub Actions self-hosted runner.

## Usage

```sh
docker run --rm -d -v /var/run/docker.sock:/var/run/docker.sock hikarin/github-actions-runner:latest --ephemeral --url "https://github.com/********" --token "****************"
```
