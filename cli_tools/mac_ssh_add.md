# Mac OSX and ssh-add

If you want to add an ssh key to your ssh agent and have it survive reboots (on mac), just add it via 
```sh
ssh-add -K /path/to/key
```
This adds it to the OSX keychain. OSX loads keys from the keychain automatically on boot.

[From stackexchange](http://unix.stackexchange.com/questions/140075/ssh-add-is-not-persistent-between-reboots)
