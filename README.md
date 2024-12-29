# SVG Timeline Diagram Action

Generates and commits SVG Timeline Diagrams from your data

---

> [!CAUTION]
> ```
>  $$\      $$\ $$$$$$\ $$$$$$$\
>  $$ | $\  $$ |\_$$  _|$$  __$$\
>  $$ |$$$\ $$ |  $$ |  $$ |  $$ |
>  $$ $$ $$\$$ |  $$ |  $$$$$$$  |
>  $$$$  _$$$$ |  $$ |  $$  ____/
>  $$$  / \$$$ |  $$ |  $$ |
>  $$  /   \$$ |$$$$$$\ $$ |
>  \__/     \__|\______|\__|
>               @1735500000   🚧
> ```

---

## Features

- 🔄 Generates SVG files from input data
- 🚀 Can be triggered manually or on file changes
- 💾 Automatically commits generated SVGs

## Usage

```yaml
name: Generate SVG Timeline Diagram
on:
  push:
    paths:
      - 'data/**'  # Trigger on data file changes
  workflow_dispatch:  # Allow manual triggers

jobs:
  generate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      
      - name: Generate Timeline diagram
      - uses: metaory/svg-timeline-action@v1
        with:
          input-path: ./data/input.json
          output-path: ./assets/output.svg
          commit-message: 'chore: update visualization'
```

## Inputs

| Input            | Description                          | Required | Default                       |
|------------------|--------------------------------------|----------|-------------------------------|
| `input-path`     | Path to input file or directory      | No       | .                             |
| `output-path`    | Where to save the generated SVG      | No       | ./output.svg                  |
| `commit-message` | Commit message for the generated SVG | No       | 'chore: update generated SVG' |

## Examples

### Basic Usage

```yaml
- uses: metaory/svg-timeline-action@v1
  with:
    input-path: ./data/stats.json
```

### Custom Output Location

```yaml
- uses: metaory/svg-timeline-action@v1
  with:
    input-path: ./data/stats.json
    output-path: ./assets/timeline.svg
```

---

LICENSE
-------

[MIT](LICENSE)
