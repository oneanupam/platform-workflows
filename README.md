# Platform Workflows

This repository contains reusable GitHub Actions workflows that can be consumed by other repositories to standardize CI/CD pipelines. The goal of this repository is to provide centralized workflow definitions so that multiple repositories can reuse the same CI/CD logic without duplicating workflow code.

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
The pre-commit framework is a powerful, language-agnostic tool for managing Git hooks. Create a .pre-commit-config.yaml file in the root of your repository. Run the below commnad from the git repo root to set up the git hook scripts into your git hooks. It will be installed at .git/hooks/pre-commit

```bash
pre-commit install
pre-commit install --config <file> # If config file has non-standard name
pre-commit validate-config # Validate .pre-commit-config.yaml files
```

now pre-commit will run automatically on git commit. Usually, it runs only for the changed files. Its good to run the hooks against all the files when adding new hooks. To manually run all pre-commit hooks on a repo, use below -

```bash
# to run hooks on all files
pre-commit run --all-files

# to run hooks on all files using a non-standard naming config file
pre-commit run --all-files --config .pre-commit-config-old.yaml

# to run individual hook
pre-commit run <hook_id>
```

Once you have pre-commit installed, adding pre-commit plugins to your project is done with the .pre-commit-config.yaml configuration file. You can generate a very basic configuration using `pre-commit sample-config`. Every time you clone a project using pre-commit running pre-commit install should always be the first thing you do.

## Contributing

Contributions are welcome! Please open issues or submit pull requests for improvements or new suggestions. Read the [contributing.md](CONTRIBUTING.md) before starting.

## License

This project is licensed under the [MIT License](LICENSE).
