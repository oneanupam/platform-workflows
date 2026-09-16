# Platform Workflows

This repository provides reusable GitHub Actions workflows for standardizing CI/CD pipelines across multiple repositories. By centralizing common workflow logic, teams can reuse the same automation patterns without duplicating workflow definitions.

## Prerequisites

To use the workflows defined in this repository, ensure the following:

- GitHub repository with GitHub Actions enabled
- Required secrets configured in the calling repository
- Access permissions to reference workflows from this repository

## Repo Layout

At a high level, these folders make up the `github.com/oneanupam/app-repo-template` repository.

- [`.github/`](./.github) - This directory contains reusable GitHub Actions workflows that can be invoked by other repositories using workflow_call.
- [`.vscode/`](./.vscode) - It contains project-specific settings and configurations to customize how VS Code behaves for the workspace.
- [`docs/`](./docs) - This folder contains the documentations related to the repository.
- [`examples/`](./examples) - This folder contains the examples to use the reusable workflows.
- [`.pre-commit-config.yaml`](.pre-commit-config.yaml) - This file contains the plugin configuration for pre-commit.
- [`.editorconfig`](.editorconfig) - This file has the configuration for the editorconfig plugin.

## Run pre-commit

This repository already includes a `.pre-commit-config.yaml`. Run the following commands to install the hooks locally:

```bash
python -m pip install pre-commit
pre-commit install
pre-commit validate-config
```

This installs the hook into `.git/hooks/pre-commit`. Once installed, pre-commit runs automatically when you commit changes. By default, it checks only the files included in the commit.

To run all hooks manually, use:

```bash
pre-commit run --all-files
pre-commit run <hook_id>
```

## Contributing

Contributions and suggestions are welcome. Before opening an issue or pull request:

1. Review the [contribution guidelines](CONTRIBUTING.md).
2. Install the pre-commit hooks and run them against your changes.
3. Open an issue for bugs or ideas, or submit a pull request with a clear description of the change.

## License

This project is licensed under the [MIT License](LICENSE).
