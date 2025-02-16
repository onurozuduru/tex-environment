# tex-environment

My base environment setup for LaTex on top of [Alpine Devcontainer image](https://github.com/devcontainers/images/tree/main/src/base-alpine).

This is designed to be used via `devcontainer cli` with `neovim`.

## Starting Container

There is a script to make binding and rebuilding easy.
It auto mounts the current directory as _workspace_.

```bash
.devcontainer/start_with_devcontainer_cli.sh
```

### Re-building

```bash
.devcontainer/start_with_devcontainer_cli.sh --rebuild
```

