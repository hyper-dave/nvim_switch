# nvim_switch

A bash script to manage and switch between different Neovim configurations.

## Features

- **Backup:** Back up your current Neovim configuration, including all relevant directories.
- **Restore:** Restore a backed-up configuration.
- **Switch:**  Switch between different configurations stored in a specified directory.
- **Clean:** Clean the current Neovim configuration or all backups.
- **Customizable:** Configure the directories for storing configurations and backups.
- **Bash Completion:** Provides bash completion for commands, options, and configuration names.

## Usage

```
nvim_switch [OPTIONS] [COMMAND] [CONFIG_NAME]
```

**Options:**

- `-c, --configs-dir <DIR>`:    Directory for Neovim configurations (default: current directory)
- `-b, --backups-dir <DIR>`:    Directory for Neovim backups (default: `$XDG_DATA_HOME/nvim_switch` or `$HOME/.local/share/nvim_switch`)
- `-f, --force-clean`:          Force clean current config before copying new config
- `-v, --version`:              Display script version
- `-h, --help`:                 Display this help message

**Commands:**

- `backup [CONFIG_NAME]`:       Back up the current Neovim configuration (optional `CONFIG_NAME` for subdirectory)
- `config [-r] [CONFIG_NAME]`:  Copy a new configuration.
                                 `-r`: Restore from backups (select from backups if `CONFIG_NAME` is not provided)
- `clean`:                      Remove the current Neovim configuration (all directories)
- `clean-backups`:              Remove all backups

## Examples

**Backup the current configuration:**

```bash
nvim_switch backup
```

**Backup the current configuration with a specific name:**

```bash
nvim_switch backup my_config
```

**Restore a configuration from backup:**

```bash
nvim_switch config -r
```

**Restore a specific configuration from backup:**

```bash
nvim_switch config -r my_config
```

**Switch to a new configuration:**

```bash
nvim_switch config new_config
```

**Clean the current configuration:**

```bash
nvim_switch clean
```

**Clean all backups:**

```bash
nvim_switch clean-backups
```

## Bash Completion

To enable bash completion, source the `nvim_switch.completion` file in your `.bashrc` or `.bash_profile`:

```bash
source nvim_switch.completion
```

## Environment Variables

- `NVIM_SWITCH_CONFIGS_DIR`:  Override the default configurations directory.
- `NVIM_SWITCH_BACKUPS_DIR`: Override the default backups directory.

## License

This script is licensed under the GPL License.
