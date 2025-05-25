# Node.js Dev Container

A minimal, repeatable Node.js dev environment using Podman Compose in WSL2. The containerized environment handles all the Node.js tooling, so you don't need Node.js installed on your host system. Perfect for consistent development environments across different machines!

## Adding to Your Project

1. Copy `compose.yml` into your project's root directory, alongside your `package.json`.
3. Launch your development environment:
   ```bash
   podman compose up
   ```

## What Happens

The setup will automatically:

- Install your project dependencies with `pnpm install`
- Start your development server with `pnpm dev`
- Bind to all interfaces so you can access it from your browser
- Mount your source code for live reloading
- Cache node_modules and pnpm store for faster subsequent starts

## Available Ports

| Port  | Framework      |
|-------|----------------|
| 3000  | Next.js        |
| 5173  | Vite/SvelteKit |
| 8080  | Fallback       |
| 24678 | HMR WebSocket  |

## Common Commands

```bash
# Start services
podman compose up

# Start in background (detached)
podman compose up -d

# View logs
podman compose logs -f

# Stop services
podman compose down

# Open interactive shell
podman compose exec node-dev sh
```

## Accessing Your Application

- Next.js: `http://localhost:3000`
- Vite/SvelteKit: `http://localhost:5173`
- Fallback: `http://localhost:8080`
