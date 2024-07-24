# Unix commands
> Note: Commands apply to my distro: `Kubuntu 24.0 LTS` codename: `noble`
## Basic commands

### Update everything
```
sudo apt update -y && sudo apt autoremove -y && sudo apt autoclean -y && sudo apt update -y && sudo apt upgrade -y && sudo snap refresh
```

## Using .bashrc
Everything in `/home/user/.bashrc` is ran when you login.

You can also set an alias to create your own commands.
```
alias vpslogin='ssh root@hostname'
```

Run
```
source ~/.bashrc
```
To apply the changes.

