# My personal dotfiles

**Warning**: Don’t blindly use my settings unless you know what that entails. Use at your own risk!

## Content

- .gitconfig
- .p10k.zsh ([powerlevel10k](https://github.com/romkatv/powerlevel10k))
- .zshrc ([oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh))
- [ITerm2](https://iterm2.com/)
  - itermcolors
  - itermkeymap
  - profile
- [VS Code](https://code.visualstudio.com/Download) settings

## Installation

### Step 1 — Install [ITerm2](https://iterm2.com/)

### Step 2 — Change Shell To ZSH

```
chsh -s $(which zsh)
```

Enter the password and it will change the shell, upon logout and login.

### Step 3 — “Oh My ZSH”

Install “Oh My ZSH”

```
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

Install [Powerline](https://github.com/powerline/fonts.git) fonts

```
git clone https://github.com/powerline/fonts.git
cd fonts
./install.sh
```

Install [ZSH-AutoSuggestion](https://github.com/zsh-users/zsh-autosuggestions) plugin

```
git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

Install [fzf](https://github.com/junegunn/fzf) plugin

```
git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
~/.fzf/install
```

Install [switch-git](https://github.com/robin-mbg/switch-git)

```
git clone https://github.com/robin-mbg/switch-git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/switch-git
```

Install [powerlevel10k](https://github.com/romkatv/powerlevel10k)

```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

Replace `.zshrc`

Update ZSH config

```
source ~/.zshrc
```

### Step 4 — Iterm colors and styles

Import `gruvbox-dark.itermcolors`, `iterm-profile.json` and `iterm-keys.itermkeymap` into Iterm


### Step 5 — VS Code settings

Replace `settings.json` and install the following extensions:

- [Auto Close Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag)
- [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)
- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [Frontend Snippets](https://github.com/andrewmoreno/frontend-snippets)
- [Gruvbox Theme](https://marketplace.visualstudio.com/items?itemName=jdinhlife.gruvbox)
- [Import Cost](https://marketplace.visualstudio.com/items?itemName=wix.vscode-import-cost)
- [Material Icon Theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme)
- [Sort lines](https://marketplace.visualstudio.com/items?itemName=Tyriar.sort-lines)
- [Template String Converter](https://marketplace.visualstudio.com/items?itemName=meganrogge.template-string-converter)
- [Turbo Console Log](https://marketplace.visualstudio.com/items?itemName=ChakrounAnas.turbo-console-log)

### Usage

I've configured `git` with some useful aliases such as:

- `git br` - lists all branches sorted by last time updated
- `git co` - `git checkout`
- `git lg` - prettier `git log`
- `git puf` - `git push origin head -f`
- `git ref` - prettier `git reflog`
- `git undo` - `git reset head~1` (it also accepts a parameter for the number of commits to undo, e.g.: `git undo 2`)
- and many more! Check them at `.gitconfig`.

Also there's an alias for quickly switching between branches using `switch-git` plugin. It is triggered simply typing `z` and a word that related to the branch name. E.g.: `z products` is the equivalent to `git checkout products`. It comes up extremelly handy specially when the branch has a long name or when we've working on different branches.

At last, `fzf` is a plugin which provides the useful feature of listing recent commands. You can run it by pressing `Ctrl + R`.
