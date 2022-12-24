# Deploy of development environment to a remote server.

# What does it do

## Installs the next software:

1. git
2. curl
3. neovim
4. tmux
5. ripgrep
6. fzf
7. bat
8. zoxide
9. lsd
10. bat-extras
11. zsh
12. ranger
13. asdf:
    - lazydocker
    - nodejs 16

note: I modified oh-my-zsh install script a bit, so it could be run silently. Probably could do it without modification, 
so you can create a pull-request if you know how to fix

## Copies the .dotfiles for the next applications

- zsh
- neovim
- tmux
- ranger
- lsd

## Installs the next zsh-features

- oh-my-zsh
- Powerlvl10k theme
- zsh-autosuggestions
- zsh-syntax-highlight


# How to use

Rename group_vars/remote.example to group_vars/remote
replace with your own data

Do the same for hosts.example -> hosts

install ansible-playbooks

run 

```
ansible-playbook -i hosts main.yml -K --tags=clear
```
to remove existing dotfiles (tmux is installed in ubuntu by default and it has its own configs already created)

Then run


```
ansible-playbook -i hosts main.yml -K --tags=clear
```
to deploy the environment
