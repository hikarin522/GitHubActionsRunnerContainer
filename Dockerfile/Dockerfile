FROM mcr.microsoft.com/powershell:lts-ubuntu-jammy

RUN apt-get update && apt-get full-upgrade -y \
    && apt-get install --no-install-recommends -y ca-certificates curl gpg git \
    && mkdir -p /etc/apt/keyrings \
    && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | gpg --dearmor -o /etc/apt/keyrings/docker.gpg \
    && echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu jammy stable" > /etc/apt/sources.list.d/docker.list \
    && apt-get update && apt-get install --no-install-recommends -y docker-ce-cli

WORKDIR /actions-runner
RUN curl -fsSL https://github.com/actions/runner/releases/latest/download/actions-runner-linux-x64-$(pwsh -c '(Invoke-RestMethod https://api.github.com/repos/actions/runner/releases/latest).tag_name.TrimStart("v")').tar.gz | tar xzvf - \
    && ./bin/installdependencies.sh

ENV RUNNER_ALLOW_RUNASROOT=1
COPY ./entrypoint.sh .
ENTRYPOINT ["./entrypoint.sh"]
