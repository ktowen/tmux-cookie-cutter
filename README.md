# Tmux Cookie Cutter

Letting you define your tmux window setup configuration, pre-run environment setup and launch programs as you start a new tmux session.

## Installation
### Installation with [Tmux Plugin Manager](https://github.com/tmux-plugins/tpm) (recommended)

Add plugin to the list of TPM plugins in `.tmux.conf`:

```shell
set -g @plugin 'AranBorkum/tmux-cookie-cutter'
```

Hit `prefix + I` to fetch the plugin and source it.

### Manual Installation

Clone the repo:

```shell
$ git clone https://github.com/AranBorkum/tmux-cookie-cutter ~/clone/path
```

Add this line to the bottom of `.tmux.conf`:

```shell
run-shell ~/clone/path/cpu.tmux
```

Reload TMUX environment:

```shell
# type this in terminal
$ tmux source-file ~/.tmux.conf
```

## Usage
Create a `.cookie-cutter.yaml` file in your `$HOME/.config/` directory _or_ a bespoke one in the root of your project. Configure this with the following values:

```yaml
<first window>:
    name: "neovim"
    command: "nvim"
    envvars:
        - VARIABLE_1=...
        - VARIABLE_2=...
    setup_command: "source .venv/bin/activate" 
<second window>:
    name: "terminal"
    command:
    envvars:
        - VARIABLE_1=...
        - VARIABLE_2=...
    setup_command: "source .venv/bin/activate" 
    panes:
        alpha:
            split_direction: "vertical"
        beta:
            split_direction: "horizontal"
            command: ./manage runserver
```
