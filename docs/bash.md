# Bash cheat sheet
!!! note annotate "Note:"

    Only applies to Ubuntu/Debian based distro's... and maybe others, who knows. 
    


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
And ==restart the shell== to apply changes.

## Live mouse location

> ``` watch -t -n 0.0001 xdotool getmouselocation ```

Get a live mouse location.