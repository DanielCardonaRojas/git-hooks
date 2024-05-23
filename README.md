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

```
curl -L -o ~/.local/bin/git-hooks https://raw.githubusercontent.com/DanielCardonaRojas/git-hooks/main/git-hooks
```

Install completions:

```sh
# Add the zsh completion file in one of the following locations:
echo $fpath
# Or source in your .zshrc
```

## Usage

### Run Hook Scripts

Manually run all scripts associated with a specific Git event:

```sh
git hooks run [pre-push|pre-commit|commit-msg]
```

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
# or deactivate all scripts for the pre-commit trigger
git hooks deactivate pre-commit
```

### Install Hook Scripts from External Sources

Fetch new hook scripts from an external repository or location:

```sh
git hooks install <source-repo>
```



### Include an external hook contributed hook after installed in the current repo.

After issuing a `git hooks install` command, you can use the `git hooks use` command to include an external hook in the current repo.

```sh
git hooks use <TAB>
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
...
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

