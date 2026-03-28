# DV8FTC Workspace

Centralized workspace for managing all DV8FTC websites.

## Quick Start

From the root `DV8FTC` folder, run:

### Run All Sites
```bash
npm run dev:all
```
This starts all websites simultaneously on different ports.

### Run Individual Sites
```bash
npm run dev:hub    # dv8ftc-hub only
```

### Build Commands
```bash
npm run build:all  # Build all sites
npm run build:hub  # Build hub only
```

## Adding New Sites

When you create a new website project:

1. Add it to this workspace folder (e.g., `projects/my-new-site`)
2. Update `package.json` scripts:

```json
"dev:all": "concurrently -n hub,newsite -c \"cyan,magenta\" \"npm run dev --prefix dv8ftc-hub\" \"npm run dev --prefix projects/my-new-site\"",
"dev:newsite": "npm run dev --prefix projects/my-new-site"
```

## Current Sites

- **dv8ftc-hub** - Central hub/network site (Port: 3000)

## Port Configuration

If sites conflict on ports, add `-p` flag in their package.json:
```json
"dev": "next dev -p 3001"
```

## Workflow

```bash
# From root DV8FTC folder:
npm run dev:all         # Start everything
npm run dev:hub         # Start only hub

# Or use individual project folders as before:
cd dv8ftc-hub
npm run dev
```
