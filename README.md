# GoFiber Docker Boilerplate

![Release](https://img.shields.io/github/release/gofiber/boilerplate.svg)
[![Discord](https://img.shields.io/badge/discord-join%20channel-7289DA)](https://gofiber.io/discord)
![Test](https://github.com/gofiber/boilerplate/workflows/Test/badge.svg)
![Security](https://github.com/gofiber/boilerplate/workflows/Security/badge.svg)
![Linter](https://github.com/gofiber/boilerplate/workflows/Linter/badge.svg)


## IDE Development

### Visual Studio Code

Use the following plugins, in this boilerplate project:
- Name: Go
  - ID: golang.go
  - Description: Rich Go language support for Visual Studio Code
  - Version: 0.29.0
  - Editor: Go Team at Google
  - Link to Marketplace to VS: https://marketplace.visualstudio.com/items?itemName=golang.Go

## Development

### Start the application 


```bash
go run app.go
```

### Use local container

```
# Shows all commands
make help

# Clean packages
make clean-packages

# Generate go.mod & go.sum files
make requirements

# Generate docker image
make build

# Generate docker image with no cache
make build-no-cache

# Run the projec in a local container
make up

# Run local container in background
make up-silent

# Run local container in background with prefork
make up-silent-prefork

# Stop container
make stop

# Start container
make start
```

## Production

```bash
docker build -t gofiber .
docker run -d -p 3000:3000 gofiber ./app -prod
```

Go to http://localhost:3000:


![Go Fiber Docker Boilerplate](./go_fiber_boilerplate.gif)

## OpenClaw Integration

[OpenClaw](https://github.com/openclaw/openclaw) is an open-source, self-hosted AI agent runtime (MIT-licensed) that connects chat platforms to an AI agent capable of executing real-world tasks on your machine.

### Key Features

- **Gateway daemon** — runs as a background service, routing messages from connected channels (WhatsApp, Discord, etc.) to an AI agent
- **Skills system** — modular, Markdown-based skills installable from [ClawHub](https://clawhub.dev), the community registry with 13,000+ skills
- **Full system access** — browser automation, file read/write, shell commands, and cron scheduling
- **Persistent memory** — remembers user preferences, projects, and context across sessions
- **Proactive automation** — schedule recurring tasks or let the agent suggest optimizations

### CLI Quick Reference

```bash
# Launch the interactive setup wizard
openclaw onboard

# Start the background gateway daemon
openclaw gateway start

# Install a skill from ClawHub
clawhub install <skill-slug>

# Run diagnostics on your installation
openclaw doctor
```

### Getting Started

1. Install OpenClaw via the [official docs](https://github.com/openclaw/openclaw)
2. Run `openclaw onboard` to configure your channels and LLM provider
3. Start the gateway with `openclaw gateway start`
4. Install skills as needed: `clawhub install github`, `clawhub install filesystem`, etc.
