# tmux-conf

Custom `tmux` configuration based on [oh-my-tmux](https://github.com/gpakosz/.tmux), with plugins and personal workflow enhancements.

## Prerequisites

* [tmux](https://github.com/tmux/tmux/wiki)

```bash
brew install tmux
```

## Installation

```bash
# 1. Clone the config repo
git clone git@github.com:desmond-45/tmux-conf.git ~/tmux-conf

# 2. Create symlinks
ln -sf ~/tmux-conf/.tmux.conf ~/.tmux.conf
ln -sf ~/tmux-conf/.tmux.conf.local ~/.tmux.conf.local

# 3. Start tmux
tmux

# 4. Reload config (inside tmux)
<Ctrl + Space> r
```

## Plugin Setup

### TPM: Tmux Plugin Manager

```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

### Plugins used

* [https://github.com/tmux-plugins/tmux-resurrect](https://github.com/tmux-plugins/tmux-resurrect)
* [https://github.com/tmux-plugins/tmux-continuum](https://github.com/tmux-plugins/tmux-continuum)

### Install plugins

Inside a running tmux session:

```bash
# Hit prefix (Ctrl + Space), then:
I
```

### Save/restore sessions

```bash
# Save:     <Ctrl + Space> Ctrl-s
# Restore:  <Ctrl + Space> Ctrl-r
```

## Aliases

Add these to your `.zshrc` or use the `tmux.aliases` file included:

```bash
alias tattach='tmux -u attach -t'
alias tmux_conf='vim ~/tmux-conf/.tmux.conf.local'
alias tnew='tmux -u new -s'
alias reload_tmux="tmux source ~/oh-my-tmux/.tmux.conf"
alias tkill='tmux kill-server'
```

## Optional Settings

* Mouse mode enabled
* History limit increased
* Prefix changed from Ctrl-b to Ctrl-Space
* Theme and plugin reload logic included

## Structure

```bash
.tmux.conf           -> Base config (linked)
.tmux.conf.local     -> Your customizations
```

## Credits

Enhanced from [https://github.com/gpakosz/.tmux](https://github.com/gpakosz/.tmux)
