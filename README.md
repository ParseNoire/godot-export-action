# Godot export action

Exports a Godot project.

## Usage

```yaml
name: my-workflow

on: push

jobs:
  export:
    runs-on: ubuntu-latest
    container: ghcr.io/parsenoire/godot-headless:latest
    steps:
      - uses: parsenoire/godot-setup-action@v1
      - uses: parsenoire/godot-export-action@v1
        with:
          path: ./export/my-project.exe
          target: Windows Desktop
```

While the image [ghcr.io/parsenoire/godot-headless](https://ghcr.io/parsenoire/godot-headless) from GitHub Container Registry is used in this example, this action should work in environments where `godot` is installed in the runner's PATH.

This example also uses [parsenoire/godot-setup-action](https://github.com/parsenoire/godot-setup-action) to make sure support files are accessible by the runner. If your runner environment handles setting up support files in a different way, you can omit or change that step.
