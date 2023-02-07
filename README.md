# Setup

Open a new terminal and init lerna:

```szh
npx lerna init
```

## lerna.json
Create lerna.json at root:
```json
// lerna.json
{
  "$schema": "node_modules/lerna/schemas/lerna-schema.json",
  "useWorkspaces": true,
  "version": "0.0.0",
  "npmClient": "npm"
}
```

## package.json

Insert the scripts
```json
// package.json
  "scripts": {
    "dev": "lerna run dev",
    "build": "lerna run build",
    "preview": "lerna run preview"
  },
```

Update the workspaces
```json
// package.json
  "workspaces": {
    "packages": [
      "remote",
      "host"
    ]
  },
```

Build the host and remote repos with:
```zsh
npm init vue@2
```

## remote/package.json & host/package.json

Insert build:watch in the scripts of package.json of remote and host
```json
// remote/package.json & host/package.json
    "build:watch": "vite build --watch",
```

Update ports in dev mode 
```json
// host/package.json
    "dev": "vite --port 5173 --strictPort",
```
```json
// remote/package.json
    "dev": "vite --port 5174 --strictPort",
```

# Install dependencies
In workspace run
```zsh
yarn install
```

# Run dev
```zsh
yarn dev
```