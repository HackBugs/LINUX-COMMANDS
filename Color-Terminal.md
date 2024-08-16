# Create Colorfull Terminal

<hr>

> ## Edit Inside this file

```sh
 gedit ~/.bashrc
```
> ## Apply Exceute this file

```sh
source ~/.bashrc
```

> ## This code use insde `bashrc` file 

```sh
#PS1='\[\033[01;35m\]\u@\h:\w\[\033[00m\]\$ '
#PS1='\[\033[48;5;82m\]\[\033[38;5;255m\]\u@\h:\w\[\033[0m\]\$ '
#export PS1='\[\033[0;32m\]\u@\h:\w\$ \[\033[0m\]'

# Define colors using RGB values
COLOR_BG='48;2;0;43;54'          # Background color (Solarized Base03)
COLOR_FG='38;2;253;246;227'      # Text color (Solarized Base0)
COLOR_PROMPT_USER='38;2;138;226;52' # Green
COLOR_PROMPT_HOST='38;2;255;88;88'  # Red
COLOR_PROMPT_DIR='38;2;33;150;243'  # Blue
COLOR_PROMPT_SYMBOL='38;2;220;50;47' # Bright Red
COLOR_GIT_BRANCH='38;2;138;226;52'  # Green

# Function to display the current git branch
git_branch() {
  local branch=$(git branch 2>/dev/null | grep '^*' | colrm 1 2)
  [ -n "$branch" ] && echo " \[\033[${COLOR_GIT_BRANCH}m\]($branch)\[\033[0m\]"
}

# Set terminal colors
set_terminal_colors() {
  # Apply background and foreground colors
  echo -e "\033[${COLOR_BG}m\033[${COLOR_FG}m"
  
  # Reset colors on exit
  trap 'echo -e "\033[0m"' EXIT
}

# Apply colors
set_terminal_colors

# Set the prompt with colors and Git branch
PS1='\[\033[${COLOR_PROMPT_USER}m\]\u\[\033[0m\]@\[\033[${COLOR_PROMPT_HOST}m\]\h\[\033[0m\] \[\033[${COLOR_PROMPT_DIR}m\]\w\[\033[0m\]$(git_branch) \[\033[${COLOR_PROMPT_SYMBOL}m\]$\[\033[0m\] '
```
