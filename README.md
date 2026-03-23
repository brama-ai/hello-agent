# Hello Agent

A standalone external agent that provides basic greetings and health reports. It is built in PHP using Symfony and serves as the reference external agent for the Brama platform.

## Prerequisites

- **PHP 8.3** or higher
- **Composer**

## Local Development Setup

To run this agent locally without Docker:

```bash
composer install
php -S localhost:8080 -t public
```

## Docker Standalone Run

You can build and run the agent locally using Docker:

```bash
docker build -t hello-agent .
docker run -p 8080:80 hello-agent
```

## GHCR Image

We publish this agent's image to the GitHub Container Registry. You can pull the pre-built image instead of building it from source:

```bash
docker pull ghcr.io/brama-ai/hello-agent:main
```

## Platform Integration

This agent comes with a `compose.fragment.yaml` which serves as its integration contract with the platform. Include the fragment in the Brama workspace stack and provide an `.env.local` based on `.env.local.example`.

## API Endpoints

| Endpoint | Description |
| -------- | ----------- |
| `/health` | Returns the health status of the agent |
| `/api/v1/manifest` | Returns the agent manifest describing its capabilities |
| `/api/v1/a2a` | The main A2A message exchange endpoint |

## Environment Variables Configuration

See `.env.local.example` for the main environment variables. Copy it to `.env.local` for local overrides.
