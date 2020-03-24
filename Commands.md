**Find files --- way better than locate**

- Very useful with pipe (|) for `mv`, `cp`, `rm` using xargs
  `find . -name '*file*' `

**awk --- use it all the time**
  `awk ' {print $2} '`

- Counting the number of lines.
I use two alternatives for that (of course there are more!!) : `awk 'END{print NR}' file` and `wc -l file`. Prefer to use `awk`. Refer this: https://stackoverflow.com/questions/28038633/wc-l-is-not-counting-last-of-the-file-if-it-does-not-have-end-of-line-character

**Copy same line multiple times**
- Repeat `text` 10 times to file.txt  

  `printf 'text\n%.0s' {1..10}` > file.txt

**Open Remote Filesystem using sshfs**
- Refer this: https://askubuntu.com/questions/774555/open-folder-gui-in-remote-machine

  `sshfs user@remotehost:/path/to/remote/folder ~/Remote`
- To unmount later
  `sudo umount /home/<USER>/Remote`

**Enable directory color in linux shell**

```
# enable color support of ls and also add handy aliases
if [ -x /usr/bin/dircolors ]; then
    test -r ~/.dircolors && eval "$(dircolors -b ~/.dircolors)" || eval "$(dircolors -b)"
    alias ls='ls --color=auto'
    #alias dir='dir --color=auto'
    #alias vdir='vdir --color=auto'

    alias grep='grep --color=auto'
    alias fgrep='fgrep --color=auto'
    alias egrep='egrep --color=auto'
fi
```
**Enable source bashrc on ssh login**

ssh login does not `source ~/.bashrc` on login. Add following to `~/.bash_profile`:
```
if [ -f ~/.bashrc ]; then
  . ~/.bashrc
fi
```
**Show only current directory name in bash prompt**

Copy following to `~/.bashrc`

```
PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\W\[\033[00m\]\$ '
```
