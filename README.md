# Local configuration

Config files for various things, as well as instructions for how to set up a new Mac laptop they way I like it. :-)

## Instructions for a new machine

There are some dependencies so they should be done roughly in this order. Please let me know if you find any errors.

#### Homebrew

- instructions at https://brew.sh

#### Sublime text 3

- `brew cask install sublime-text`
- Open ST3, install package control (shift-cmd-P), and then close it
- In `~/Library/Application Support/Sublime Text 3/Packages`, do:
    - `rm -rf User/`
    - `ln -s ~/configuration/sublime-text-3/Packages/User/ User`
- Re-start Sublime, then all missing packages should be installed automatically.

#### git

- `brew install git`
- Enter the following into `~/.gitconfig`:
```
[user]
    name = <NAME HERE>
    email = <EMAIL>
[core]
    excludesfile = ~/configuration/git/.gitignore_global
[credential]
    helper = osxkeychain
[include]
    path = ~/configuration/git/.gitconfig-shared
```

#### Get the configuration stored here

- Clone this repo from your home dir
    - `cd ~`
    - `git clone https://github.com/eengxy/configuration.git`
- Create a dir to store your dotfiles
    - `$ mkdir ~/configuration/dotfiles/<computername>`

#### zsh

- Install using `brew install zsh`
- Type `zsh` in a terminal window and go through the configuration wizard
- Set it to be the default shell using
    - `sudo sh -c "echo $(which zsh) >> /etc/shells"`
    - `chsh -s $(which zsh)`
- move your dotfile and create a symlink: (can be skipped if planning to install oh-my-zsh)
    - `mv ~/.zshrc ~/configuration/dotfiles/<computername>/`
    - `ln -s ~/configuration/dotfiles/<computername>/.zshrc ~/.zshrc`

#### iterm2

- `brew cask install iterm2`
- Configure it to load preferences from the configuration dir
- Install shell integration, see: https://www.iterm2.com/documentation-shell-integration.html
    - If you are planning to use the spaceship prompt and want to disable the blue triangle added by shell integration, you can turn it off by going in to Preferences > Profiles > (your profile) > Terminal, scroll down to "Shell Integration", and turn off "Show mark indicators".

#### oh-my-zsh

- Use curl, see here: https://github.com/robbyrussell/oh-my-zsh
- move your dotfile and create a symlink:
    - `mv ~/.zshrc ~/configuration/dotfiles/<computername>/`
    - `ln -s ~/configuration/dotfiles/<computername>/.zshrc ~/.zshrc`

#### zsh-autosuggestions

- Using brew, see: https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md#macos-via-homebrew

#### zsh-completions

- `brew install zsh-completions` and follow instructions

#### zsh-syntax-highlighting

- `brew install zsh-syntax-highlighting` and follow instructions

#### Review your dotfile

- Add some plugins for oh-my-zsh if you want
- Check out the existing ones in the dotfiles dir and copy some settings

#### zsh theme 

Pick one of:
##### powerlevel9k theme 

- Using homebrew or git, see: https://github.com/bhilburn/powerlevel9k/wiki/Install-Instructions#macos-with-homebrew

##### spaceship
- see: https://github.com/denysdovhan/spaceship-prompt
    - If using iterm2 terminal integration, set `SPACESHIP_PROMPT_ADD_NEWLINE=false
` in `.zshrc` to not double-add newlines

#### powerlevel fonts

- Download at least one powerlevel font. Open the downloaded font and press "Install Font". Set this font in iTerm2 (iTerm → Preferences → Profiles → Text → Change Font). Then restart iTerm2 for all changes to take effect.
		- Meslo: https://github.com/powerline/fonts/blob/master/Meslo%20Slashed/Meslo%20LG%20M%20Regular%20for%20Powerline.ttf
		- SourceCodePro: https://github.com/powerline/fonts/blob/master/SourceCodePro/Source%20Code%20Pro%20for%20Powerline.otf
		- Others: https://github.com/powerline/fonts

#### BTT (Better Touch Tool)

- `brew cask install bettertouchtool`
- Import trigger file from configuration dir
- Download and install Golden Chaos touchbar configuration - Don't forget to update configuration according to instructions

#### Omnifocus

- `brew cask install omnifocus`

#### Launchbar

- `brew cask install launchbar`

#### Dropbox

- `brew cask install dropbox`

#### Google Chrome

- `brew cask install google-chrome`

#### Miniconda

- `brew cask install miniconda`
- `conda init zsh`
- (If this fails, add this path to `.zshrc`: `export PATH="/usr/local/miniconda3/bin:$PATH"`)
- Finally do a `conda update conda`
- If using spaceship prompt:
    - disable native conda prompt by running `conda config --set changeps1 False`
    - Optionally, add the line `[[ $CONDA_DEFAULT_ENV == base ]] && return` to the file `.oh-my-zsh/custom/themes/spaceship-prompt/sections/conda.zsh` in order to remove the conda env section when the base environment is activated


### TBD

#### Evernote

#### Mactex

#### Skim

#### Spotify


