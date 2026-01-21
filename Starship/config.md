# Starship configuration

```toml
scan_timeout = 10
command_timeout = 2000
add_newline = true


format = """$all  $fill  $cmd_duration$jobs$c$nodejs$python$time$line_break\
$character[❯](bold white) """

[jobs]
symbol = "+ "
number_threshold = 1
symbol_threshold = 1

[character]
success_symbol = "[](bold green)"
error_symbol = "[](bold red)"
vicmd_symbol = "[❮](green)"


[time]
disabled = false
time_format = "%I:%M %p"
use_12hr = true
style = "bold white"
format = "[󰄉 $time]($style)"

[fill]
#symbol = "─"
#symbol = "-"
symbol = " "

[cmd_duration]
min_time = 1000
format = "[󱦟$duration](bold yellow)  "

[username]
style_user = "blue bold"
style_root = "black bold"
format = " [$user]($style) "
disabled = false
show_always = true

[directory]
truncation_length = 1
truncation_symbol = " "
read_only_style = "197"
read_only = "  "
format = "in [$path]($style)[$read_only]($read_only_style) "

[directory.substitutions]
"~" = " home"
"C:/" = " root "
"D:/" = " root "
"E:/" = " root "

[git_branch]
symbol = " "
truncation_length = 30
style = "bold purple"
format = "on [$symbol$branch]($style) "


[git_status]
format = '[\[ $all_status$ahead_behind\]]($style) '
style = "bold green"
conflicted = "🏳"
up_to_date = " "
untracked = "[󰋖](bold red) "
ahead = "⇡ "
diverged = "⇕⇡x${ahead_count}⇣x${behind_count} "
behind = "⇣ "
stashed = " "
modified = "󱈸 "
staged = '[++$count](green) '
renamed = " "
deleted = "[ ](bold red)"


#[git_status]
#format = '[\[ $all_status$ahead_behind\]]($style) '
#style = "bold green"
#conflicted = "🏳"
#up_to_date = " "
#untracked = "[󰋖 x${count}](bold red) "
#ahead = "⇡x${count} "
#diverged = "⇕⇡x${ahead_count}⇣x${behind_count}"
#behind = "⇣x${count}"
#stashed = " "
# modified = " x${count} "
#staged = '[++$count](green) '
#renamed = " x${count} "
#deleted = "[ x${count}](bold red) "


[nodejs]
format = "[󰎙 $version](bold green)  "
detect_files = ["package.json", ".node-version"]
detect_folders = ["node_modules"]

[package]
symbol = " "
style = "bold red"
format = "is [${symbol}${version}]($style)"

[python]
symbol = " "
format = '[${symbol}(${version}) (\[$virtualenv\])]($style) '
style = "bold green"
pyenv_prefix = "venv"
python_binary = ["./venv/bin/python", "python", "python3", "python2"]
detect_extensions = ["py"]
version_format = "v${raw}"

[c]
symbol = " "
format = "[$symbol$version](bold yellow)  "

```


## New mininal theme

```toml

ommand_timeout = 2000

add_newline = true

format = """$all$fill$cmd_duration$jobs$dotnet$c$nodejs$python$time$line_break\
$character"""

[fill]
symbol = " "

[git_branch]
symbol = " "
truncation_length = 30
style = "bold purple"
format = "❯ [$symbol$branch]($style) "

[git_status]
format = '[\[$all_status$ahead_behind\]]($style) '
style = "bold green"

[cmd_duration]
min_time = 1000
format = "[$duration](bold yellow)  "

[directory.substitutions]
"~" = " home"

# use it for windows
"C:/" = " root "
"D:/" = " root "
"E:/" = " root "


[time]
disabled = false
time_format = "%I:%M %p"
use_12hr = true 
style = "bold white"
format = "[ $time]($style)"

[username]
style_user = "blue bold"
style_root = "black bold"
format = " [$user]($style) "
disabled = false
show_always = true

[directory]
truncation_length = 1
truncation_symbol = " "
read_only_style = "197"
read_only = "  "
format = "❯ [$path]($style)[$read_only]($read_only_style) "

[nodejs]
format = "[ $version](bold green)  "
detect_files = ["package.json", ".node-version"]
detect_folders = ["node_modules"]

[package]
symbol = " "
style = "bold red"
format = "❯ [${symbol}${version}]($style)"

[python]
symbol = " "
format = '[$symbol$version( \[$virtualenv\]) ]($style) '
style = "bold green"
pyenv_prefix = "venv"
python_binary = ["./venv/bin/python", "python", "python3", "python2"]
detect_extensions = ["py"]
version_format = "v${raw}"

[c]
symbol = " "
format = "[$symbol$version](bold yellow)  "

[dotnet]
symbol = ' '
version_format = "${raw}"
format = "[$symbol($version )( $tfm )]($style)  "
style = "bold blue"
heuristic = false  
```


## New Version

```toml
# ~/.config/starship.toml

add_newline = true
command_timeout = 1000
format = """$os$username$directory$git_branch$git_status$fill$python$line_break\
$character"""


# ---

[os]
format = '[$symbol](bold white) '
disabled = false

[os.symbols]
Windows = ' '
Ubuntu = ''
Macos = '󰀵'

[fill]
symbol = " "

# ---

# Shows the username
[username]
style_user = 'blue bold'
style_root = 'black bold'
format = '[$user]($style) '
disabled = false
show_always = true


# Shows current directory
[directory]
truncation_length = 1
truncation_symbol = " "
home_symbol = ' home'
read_only_style = '197'
read_only = '  '
format = 'at [$path]($style)[$read_only]($read_only_style) '

# Shows current git branch
[git_branch]
symbol = ' '
format = 'on [$symbol$branch]($style)'
style = 'bold purple'

# Shows current git status
[git_status]
format = '([ \( $all_status$ahead_behind\)]($style) )'
style = 'bold green'
conflicted = '[ confliced=${count}](red) '
up_to_date = '[󰘽 up-to-date](bold green) '
untracked = '[󰋗 untracked=${count}](red) '
ahead = ' ahead=${count}'
diverged = ' ahead=${ahead_count}  behind=${behind_count}'
behind = ' behind=${count}'
stashed = '[ stashed=${count}](green) '
modified = '[󰛿 modified=${count}](yellow) '
staged = '[󰐗 staged=${count}](green) '
renamed = '[󱍸 renamed=${count}](yellow) '
deleted = '[󰍶 deleted=${count}](red) '

[python]
symbol = " "
format = '[$symbol$version( \[ $virtualenv \]) ]($style)'
style = "bold green"
pyenv_prefix = "venv"
python_binary = ["./venv/bin/python", "python", "python3", "python2"]
detect_extensions = ["py"]
version_format = "v${raw}"
```

## current version
```toml
format = """
$username\
$hostname\
$directory\
$git_branch\
$git_state\
$git_status\
$cmd_duration\
$fill\
$all\
$docker_context\
$package\
$python\
$line_break\
$character"""


[fill]
symbol = ' '

[package]
format = '[ $version  ](008 bold)'

[directory]
truncation_length = 1
truncation_symbol = " "
home_symbol = ' home'
read_only_style = '197'
read_only = '  '
format = '[$path]($style)[$read_only]($read_only_style) '

[character]
success_symbol = "[❯](purple)"
error_symbol = "[❯](red)"
vimcmd_symbol = "[❮](green)"

[git_branch]
format = 'git:[$branch]($style)'
style = "bright-black"

[git_status]
format = ' ([\[$all_status$ahead_behind\]]($style)) '
style = "blue"

[git_state]
format = '([$all_status$ahead_behind]($style)) '
style = "bright-black"

[cmd_duration]
format = "[$duration]($style) "
style = "yellow"

[python]
format = '( ${version})[(: $virtualenv )]($style)'
style = "bright-black"

[nodejs]
format = '[ $version  ](bright-white)'


[docker_context]
format = 'via [🐋 $context](blue bold)'
detect_files = ['docker-compose.yml', 'docker-compose.yaml', 'Dockerfile']
```
