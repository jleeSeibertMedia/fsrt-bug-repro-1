This project uses [turborepo](https://turborepo.org/) to establish a local build pipeline within the monorepo.# Build chain
Turborepo builds every package by it's own in the order of dependencies.

```
           +--> web ----+
bridge ----+            +---> forge/dist
manifest --+--> forge --+
```

1. `bridge` and `manifest` will be built first parallely
2. then
3. `web` will be built after `bridge`
4. `forge` will be built after `bridge` and `manifest` and `web`
5. The result is an app bundle in `forge/dist` which is the root to use `@forge/cli` to register, deploy and install the app.
