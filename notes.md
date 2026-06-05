# Terminal Setup

| **Tool**    | **Replacing** | **Key Upgrade**                             |
| ----------- | ------------- | ------------------------------------------- |
| **zoxide**  | `cd`          | "Teleportation" via memory/habits.          |
| **eza**     | `ls`          | Icons, colors, and Git status visibility.   |
| **bat**     | `cat`         | Syntax highlighting and line numbers.       |
| **ripgrep** | `grep`        | Speed and automatic `.gitignore` awareness. |
| **fd**      | `find`        | Simplified syntax and faster execution.     |

you forgot ohmyzsh! (find cmd)


```bash
# Download Ghostty & ohmyzsh and then;

git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
brew install eza bat ripgrep fd fzf zoxide starship
brew install --cask font-jetbrains-mono-nerd-font

# ctrl + r to use fuzzy search
```

```bash
vim ~/.config/ghostty/config
# Slap your ghostty config in

# Slap your .zshrc in and make sure you've got the following plugins


# Add this to your .zshrc
plugins=(
git
zoxide
zsh-autosuggestions
zsh-syntax-highlighting
)

# As well as;

# Init tools
# Init Starship Prompt
eval "$(starship init zsh)"

# Init Zoxide (Smarter cd)
eval "$(zoxide init zsh)"

# Init fzf (Fuzzy Finder)
source <(fzf --zsh)

# Modern Command Aliases
alias ls="eza --icons --group-directories-first"
alias ll="eza -lh --icons --grid"
alias cat="bat"
alias grep="rg"
alias find="fd"

```

```bash
# Install git and run
git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"

# Don't forget your SSH keys
```


### Extra git commands
`git reset --soft HEAD~` resets last commit but keeps them staged
`git push origin [BRANCH] --force`
`git diff HEAD^`
### Extra commands
realpath = getting the real path of something, e.g.
`source` - 
`export` - 
`realpath openjdk-26.0.1`

Android Nuke
`./gradlew :yourAppNameHere:assembleDebug --rerun-tasks`


### Other software
* Rectangle
* BetterDisplay
	* You need to enable flexible scaling however


# Claude Notes
```bash
/init
```
scans code base
creates a summary to CLAUDE.md
This file is included in every request


  shift + tab allows claude code to freely write files without needing to ask for permission every time.


### CLAUDE.md
Guides Claude through codebase via important commands, arch, coding style, etc and allows you to give Claude specific or custom directions

### Three Claude files
*All but project level is optional*
#### CLAUDE.md (project level)
* generated with `/init`
* Commit to source control
* Shared with other engineers
#### CLAUDE.local.md (local) 
* Not shared with other engineers
* Contains personal instructions & customizations

#### ~/.claude/CLAUDE.md(global)
* Used with all projects on your machine
* Contains instructions that you want Claude to follow on all projects


### How to edit CLAUDE.md
`#` - Puts us in memory mode and can update it that way
Or add manually



`@` to reference files. E.g. "how does the the auth in this project work @someAuthFile"

another example: 
```bash
#/Database schema is defined in @project/schema.prisma. Reference this anytime you need to udnerstand the structure of data stored inthe database.

# The above gets slapped in your Claude.md file - Note this gets referenced every request.

```



## Making Changes

`ctrl + v` used for pasting screenshots, not cmd (even on mac)


>[!note]
>Taking screenshots of what you're referring to seems to be the best way to Claude to understand what you're talking about. Screenshot driven development it seems.


### For harder tasks:

#### Plan mode
enter with pressing `shift + tab` twice, or just once if you've already got edit permissions. Claude will do much more research over the contents of your project.

### Thinking modes (adds more token budget)
(least to most)
* Think
* Think more
* Think a lot
* Think longer
* Ultrathink

You can use both of the above


Plan = use for breadth (or lots of steps)
Think = for depth


> [!NOTE] Good git assistant
> Can write good commit msgs etc


esc - stop what you're doing
use # to add a memory about the correct approach
esc X2 - rewind a conversation

/compact - clear convo history, but keep summary of context (more focus basically)

/clear dump whole convo

/install github app for github actions

/hooks tool




> [!Warning] Claude hook use case
> Man is writing a hook to make a new instance of Claude to double check queries folder then yeet the findings to og instance of Claude so that doesn't accidentally duplicate queries. 
> 
> Surely it's easier to just write the bloody query. This is a little crazy, it also is going to run every time you try to edit something 




