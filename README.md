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
| `api_key` | Agentuity API key for authentication | Yes | - |
| `project_dir` | Path to the project directory | No | "." |

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
      - uses: actions/checkout@v3
      - uses: agentuity/deploy-action@v1
        with:
          api_key: ${{ secrets.AGENTUITY_API_KEY }}
```