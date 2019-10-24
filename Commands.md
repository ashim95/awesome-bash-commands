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
