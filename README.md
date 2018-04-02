# bash-nanorc
A better .nanorc for Bash scripts

Taken from http://www.criticalsecurity.net/index.php/topic/32987-proper-bash-scripting-syntax-highlighting-in-nano (the forum site is dead, but can be viewed via the 2012-05-05 14:29:50 version on web.archive.org).

***Originally posted by user Pilot on 22 May 2010 - 09:00 PM:**

For those interested in getting proper syntax highlighting for Bash scripting in nano, I've just modified the sh highlight file and come up with this:*

```
## Here is an example for Bourne shell scripts.
##
syntax "bash" "\.sh$"
header "^#!.*/(ba|k|pdk)?sh[-0-9_]*"
icolor brightgreen "^[0-9A-Z_]+\(\)"
color green "\<(case|do|done|elif|else|esac|exit|fi|for|function|if|in|local|read|return|select|shift|then|time|until|while)\>"
color green "(\{|\}|\(|\)|\;|\]|\[|`|\\|\$|<|>|!|=|&|\|)"
color green "-[Ldefgruwx]\>"
color green "-(eq|ne|gt|lt|ge|le|s|n|z)\>"
color brightblue "\<(cat|cd|chmod|chown|cp|echo|env|export|grep|install|let|ln|make|mkdir|mv|rm|sed|set|tar|touch|umask|unset)\>"
color brightyellow ""(\\.|[^"])*""
icolor brightred "\$\{?[0-9A-Z_!@#$*?-]+\}?"
color brightyellow "'(\\.|[^'])*'"
color cyan "(^|[[:space:]])#.*$"
color ,green "[[:space:]]+$"
```

*The difference between this and sh is that if a variable is within double quotes ("") it will be properly coloured as a variable. If it is within single quotes ('') it wont be (as it wouldnt be expanded). Also, any quotes within comments wont be coloured, as they are commented.*

*I've submitted this to the nano maintainer, left to see what happens.*

*If you want to use this, save the above to ```/usr/share/nano/bash.nanorc``` and edit ```~/.nanorc``` and add ```include /usr/share/nano/bash.nanorc```*
