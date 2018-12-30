# Local configuration

Config files for various things

## Initial setup

First clone this repo to `~/configuration`

### Sublime Text

- Install and open ST3. Then close it.
- In `~/Library/Application Support/Sublime Text 3/Packages`, do:
```
rm -rf User/
ln -s ~/configuration/Sublime\ Text\ 3/Packages/User/ User
```
- Re-start Sublime, then all missing packages should be installed automatically.

### git

- `Brew install git`
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
- (Delete the osxkeychain helper if not on a mac)
