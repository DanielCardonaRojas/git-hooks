# git-hooks

`git-hooks` is a lightweight, dependency-free Git hook management system implemented using pure shell scripts. It leverages a directory-based structure to organize and manage Git hooks, providing simple commands for setup, activation, deactivation, and execution of hook scripts.

## Features

- **No Dependencies**: Pure shell script implementation without the need for external languages or tools.
- **Directory Structure**: Organize hook scripts in `.githooks/<GIT_EVENT>/<SCRIPT>` directories.
- **Multiple Scripts per Event**: Supports multiple scripts for a single Git event.
- **Easy to Use Commands**: Simple commands for setting up hooks, activating/deactivating scripts, and fetching new hooks from external sources.
- **Zsh Completion**: Provides tab completion for subcommands and arguments.
- **Relative Path Execution**: Works from any directory within the Git repository.

## Installation

Clone the `git-hook` repository to your local machine:

```sh
git clone https://github.com/yourusername/git-hook.git
```

Add the `git-hook` script to your `PATH`:

```sh
export PATH=$PATH:/path/to/git-hook
```

## Usage

### Setup

Set up the necessary directories and initialize Git hooks:

```sh
git hooks setup
```

### Activate a Hook Script

Activate a script for a specific Git event:

```sh
git hooks activate <event> <script>
```

Example:

```sh
git hooks activate pre-commit my-script.sh
```

### Deactivate a Hook Script

Deactivate a script for a specific Git event:

```sh
git hooks deactivate <event> <script>
```

Example:

```sh
git hooks deactivate pre-commit my-script.sh
```

### Install Hook Scripts from External Sources

Fetch new hook scripts from an external repository or location:

```sh
git hooks install <source-repo>
```

Example:

```sh
git hooks install https://github.com/anotheruser/githooks-repo.git
```

### Run Hook Scripts

Manually run all scripts associated with a specific Git event:

```sh
git hooks run <event>
```

Example:

```sh
git hooks run pre-commit
```

## Directory Structure

The `git-hook` system uses a directory-based structure for managing hook scripts:

```
.githooks/
├── pre-commit/
│   ├── script1.sh
│   └── script2.sh
├── pre-push/
│   └── script3.sh
└── commit-msg/
    └── script4.sh
```

## Zsh Completion

To enable Zsh completion for the `git-hook` commands, add the following to your `.zshrc`:

```sh
source /path/to/git-hook/git-hook-completion.zsh
```

## Contribution

Feel free to contribute to this project by submitting issues or pull requests. For major changes, please open an issue first to discuss what you would like to change.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---

This README file provides an overview of the `git-hook` project, including installation instructions, usage examples, and information about the directory structure and Zsh completion. Adjust the URLs and paths to match your actual repository and file locations.
