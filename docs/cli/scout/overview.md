# docker scout

Command line tool for Docker Scout.

> `docker scout` is a Docker CLI plugin. See the [Docker Scout CLI reference](https://docs.docker.com/engine/reference/commandline/scout/).

## Usage

```text
docker scout [command]
```

## Subcommands

See [TOC](./toc.md) for the complete subcommand list.

## Legacy note

- When you have built an image, it is good practice to scan it for security vulnerabilities using the docker scan command. Docker has partnered with Snyk to provide the vulnerability scanning service.

```bash
sudo docker scan getting-started
```

> `docker scan` was the legacy Snyk-based command and is replaced by Docker Scout (e.g. [docker scout cves](./cves/overview.md)).
