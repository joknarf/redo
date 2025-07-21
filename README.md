# redo
bash/zsh interactive history menu / autocompletion
replacement for bash/zsh <kbd>Ctl</kbd><kbd>R</kbd> and <kbd>Esc</kbd><kbd>/</kbd> to search in history and re-execute/re-edit commands.

## usage

```shell
$ git clone https://github.com/joknarf/redo
$ source redo/redo
```
or direct source from github repository:
```shell
$ source <(curl -Ls https://raw.githubusercontent.com/joknarf/redo/main/redo)
```

Then on command line:  

* <kbd>Shift</kbd><kbd>Tab</kbd> or <kbd>Esc</kbd><kbd>/</kbd> or <kbd>Ctl</kbd><kbd>R</kbd> to access history menu
* you can put pattern on command line + <kbd>Shift</kbd><kbd>Tab</kbd> or <kbd>Esc</kbd><kbd>/</kbd> or <kbd>Ctl</kbd><kbd>R</kbd> to filter and access history menu
* in menu enter pattern to filter/re-filter history
* select command line with arrows or enter number and press enter
* you can then edit the command line before execution

![redo](https://github.com/joknarf/redo/assets/10117818/125a2e72-0a89-4c67-bac6-2276813cff68)

## keys in menu

|key                             | action                                                |
|--------------------------------|-------------------------------------------------------|
|<kbd>⇩</kbd>                    | select next item                                      | 
|<kbd>⇧</kbd>                    | select prev item                                      |
|<kbd>End</kbd>/<kbd>⇨</kbd>     | select last item                                      |
|<kbd>Home</kbd>/<kbd>⇦</kbd>    | select first item                                     | 
|<kbd>PgUp</kbd>/<kbd>Ctl</kbd><kbd>F</kbd>| next page                                   |
|<kbd>PgDn</kbd>/<kbd>Ctl</kbd><kbd>B</kbd>| previous page                               |
|<kbd>Esc</kbd>                  | exit                                                  |
|<kbd>Ctrl</kbd><kbd>A</kbd>     | use all screen to display menu                        |
|<kbd>Enter</kbd>/<kbd>Tab</kbd> | put selected on command line                          |
|<kbd>Tab</kbd>                  | apply filter/new filter                               |
|<kbd>Del</kbd>/<kbd>F8</kbd>    | delete item from history file                         |

* filter pattern can be applied entering text
* selection can be done entering item number

## delete history commands

To delete command from current shell history and `$HISTFILE` use `redodel` command then chose command and press <kbd>Del</kbd> or <kbd>F8</kbd>.  

Using <kbd>Del</kbd>/<kbd>F8</kbd> when using redo bind key (<kbd>Esc</kbd><kbd>/</kbd> or <kbd>Ctl</kbd><kbd>R</kbd>) will not remove command from current shell history (line editing limitation), but the `$HISTFILE` will be purged from the command.  

When deleting history in `$HISTFILE` using redo bind key, set the following options to ensure the history is not written later in `$HISTFILE` by shell.

* zsh options to set :
  ```zsh
  setopt appendhistory
  setopt incappendhistory
  ```

* bash options to set :
  ```
  shopt -s histappend cmdlist
  PROMPT_COMMAND='history -a'
  ```

## limitations

* zsh on ubuntu 22 : in vi mode, to have <kbd>Esc</kbd><kbd>/</kbd> correctly binded, you need to put in `~/.zshenv`:
  ```
  skip_global_compinit=1
  ```
