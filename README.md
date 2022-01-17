## 2 configuration
1. function of file
`commmand.py`: some custom command(:xxx)
`rc.conf`: configuration
`rifle.conf`: application of default open
`scope.sh`: how to preview document

2. get default configuration
```shell
ranger --copy-config=rc
```
To stop ranger from loading both the default and your custom `rc.conf`,
please set the environment variable `RANGER_LOAD_DEFAULT_RC` to `FALSE`.

3. get all configuration
```shell
ranger --copy-config=all
```

## 2 manual set configuration
1. make file to `~/.config/ranger/rc.conf`

2. make environment variate `RANGER_LOAD_DEFAULT_RC` `FALSE`

3. install `w3m`

4. setting `scope.sh`
```shell
set preview_images true
set preview_images_method w3m
```

5. map jump
```shell
map gb cd ~/documents/books/
```

6. rename one or more file/directory
```shell
map cw eval fm.execute_console("bulkrename") if fm.thisdir.marked_items else fm.open_console("rename")
```

7. else map
```shell
map f console scout -ftsea%space
```

8. custom map shell
```shell
map <xxx> console shell <command>
```


## 2 go to current directory, when quit `ranger` 
Add to end of `.bashrc` 
```shell
alias ra='ranger --choosedir=$HOME/.config/ranger/.rangerdir; RANGERLASTDIR=`cat $HOME/.config/ranger/.rangerdir`; cd "$RANGERLASTDIR"'
```

## 2 Auto start ranger, when open terminal

* Add to end of `bashrc` 
```shell
//cd `cat $HOME/.config/ranger/.rangerdir`
//cd $HOME
//ra
```

* Command for open computer
```shell
st -e bash -c "ranger --choosedir=$HOME/.config/ranger/.rangerdir;RANGERLASTDIR=`cat $HOME/.config/ranger/.rangerdir`;echo "$RANGERLASTDIR";cd "$RANGERLASTDIR" ;exec bash";
```

## 2 use
### move
```shell
j					down
k					up
h					left
l					right
q					quit
gi					cd ~/Github
gg					top of current dir
%					middle of current dir
G					end of current dir
[					move to up dir of same grade
]					move to down dir of same grade
H					move to pre position of history
L					move to next postion of history

/					search. use 'tab' can master it. use 'n' to search next one. use 'N' to search pre one
fc					new dir
cw					rename
yy					copy file
yp					copy path and name of file

dd					cut file/dir or cancel operate

p					paste
pp					paste and no override
po					paste and override

i					view the text. insert some things in front of name
e					edit the text
a					insert some things between name and .*

dD					delete

:bulkrename			rename by vim

<space>				select
v					select all file in current dir

dU					show size of dir or file

o					order by some model
oc					...
om					...

r					select method of open file

<ctrl>h				show hide file
zh

m<key>				create mark
`<key>				open mark
um<key>				remove mark

u					cancel option
R					refresh current directory
w					go to task manager(such as process of copy)
					dd exit a task
					J decrease grade of task
					K increase grade of task
q					exit ranger
S					exit ranger and go to directory of ranger stay
					add follow to shell rc: alias ranger='ranger --choosedir=$HOME/.config/ranger/.rangerdir; RANGERLASTDIR=`cat $HOME/.config/ranger/.rangerdir`; cd "$RANGERLASTDIR"'
s/!	use shell command
:shell <command>	execute command by shell
console	<command>	execute command by ranger

... 				compress
... 				dowload file
```

## 2 plugins
* `fzf`


## 2 attention
1. Don't patch `allpha` of terminal (can't preview picture) 


## 2 task
1. When login computer, open ranger automatic
2. set default app
3. add `fzf` plugins
4. `unmap q`
5. output today task in terminal

