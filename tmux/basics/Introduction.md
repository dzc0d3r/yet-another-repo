# Tmux - Terminal Multiplexer

## What is Tmux?

Tmux is a terminal multiplexer. It allows you to manage multiple terminal sessions from a single screen, making it perfect for working with multiple programs in a single terminal window. This is especially useful for developers, system administrators, and anyone who spends a lot of time in the terminal.

With Tmux, you can:

- Split your terminal into multiple panes.
- Create, manage, and navigate between multiple terminal sessions.
- Detach from a session and reattach to it later, keeping your processes running in the background.
- Work more efficiently by switching between different workflows easily.

## Why Use Tmux?

- **Persistence**: Even if you close your terminal or lose your SSH connection, your Tmux sessions will continue running.
- **Efficiency**: You can have multiple terminal windows and split panes inside one session, reducing the need for multiple terminal tabs.
- **Flexibility**: Detach and reattach sessions on the go, so you can start your work on one machine and continue it on another.
- **Organized Workflow**: Organize your tasks by separating them into different windows and panes.
- **Customizable**: Tmux is highly customizable. You can define your key bindings, change the layout of panes, and more.

## Getting Started with Tmux

Here are a few commands to help you get started:

### 1. Installing Tmux

To install Tmux on your system:

- On **Ubuntu/Debian** based distos:  
```bash
  sudo apt update
  sudo apt install tmux
```
- On **macOS** (with **Homebrew**):
```bash
brew install tmux
```
- On **Fedora**
```bash
sudo dnf install tmux
```
- On **Arch** based distros:
```bash
sudo pacman -S tmux
```
### 2. Basic usage
Start new session:
```bash
tmux
```
the above command will start a new tmux session without a name 
To start a new tmux session with a name so you can easily attach to it later use:
```bash
tmux new -s <session-name>
```
- List all session 
```bash
tmux ls
```
Output something like:
```bash
0: 1 windows (created Wed Oct 23 21:31:53 2024)
laravel: 1 windows (created Wed Oct 23 21:32:14 2024)
```

- To detach from a session press `CTRL+b` followed by `d` .. in fact you will notice that you will use `CTRL+b` a lot wich you can map to another key however i will recommend not doing so.

- To reattach to a session you detached from previously: 
```bash
tmux attach -t <session-name>
```
- To kill a session:
```bash 
tmux kill-session -t <session-name>
```
### 3. Managing Panes 

- To split horizontally: `<CTRL+B>` + `%` 
- To split vertically : `<CTRL+B>` + `"` 
- To switch between panes: `<CTRL+B>` + arrow keys (left,right,up,down)
- To close a pane: `<CTRL+B>` + x 
### 4. Managing Windows
- To create a new window: `<CTRL+B>` + `c` 
- To navigate between windows: `<CTRL+B>` + `n` for next and `p` for previous 
- To rename a window: `<CTRL+B>` + `,` 

## Further Customization

To customize your Tmux configuration, you can create a .tmux.conf file in your home directory:
```bash
touch ~/.tmux.conf
```
Here, you can define your custom key bindings, set pane colors, change the status bar, and more. For example, this configuration changes the default key binding to use `<CTRL+A>` instead of `<CTRL+B>`:
```bash
# Change the prefix from Ctrl-b to Ctrl-a
set -g prefix C-a
unbind C-b
bind C-a send-prefix
```

## Conclusion:
Tmux is a powerful tool for anyone working with multiple terminal sessions or needing to maintain long-running processes in the background. With its session management, pane splitting, and customization options, Tmux can streamline your terminal workflow.
