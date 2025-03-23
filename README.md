<div align="center">
    <img src=".github/Agentuity.png" alt="Agentuity" width="100"/> <br/>
    <strong>Build Agents, Not Infrastructure</strong> <br/>
<br />

<a href="https://github.com/agentuity/sdk-js/blob/main/README.md"><img alt="License" src="https://badgen.now.sh/badge/license/Apache-2.0"></a>
<a href="https://discord.gg/vtn3hgUfuc"><img alt="Join the community on Discord" src="https://img.shields.io/discord/1332974865371758646.svg?style=flat"></a>
</div>
</div>


# Agentuity Deploy Action

A GitHub Action to deploy Agentuity projects to the cloud.

## Usage

```yaml
- uses: agentuity/deploy-action@main
  with:
    api_key: ${{ secrets.AGENTUITY_API_KEY }}
    project_dir: ./  # Optional, defaults to "."
```

## Inputs

| Name | Description | Required | Default |
|------|-------------|----------|---------|
| `api_key` | Agentuity API key for authentication | Yes | NA |
| `project_dir` | Path to the project directory | No | . |

## Example

```yaml
name: Deploy Agentuity Project

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3
      - name: Install Bun
        uses: oven-sh/setup-bun@v1
        with:
          bun-version: latest
      - name: Deploy Agentuity Project
        uses: agentuity/deploy-action@v1
        with:
          api_key: ${{ secrets.AGENTUITY_API_KEY }} 
```
