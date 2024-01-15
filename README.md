# redo
bash/zsh interactive history menu  
replacement for bash/zsh `Ctl-R` and `Esc+/` to search in history and re-execute/re-edit commands.

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
* `Esc+/` or `Ctl-R` to access history menu
* you can put pattern on command line + `Esc+/` or `Ctl-R` to filter and access history menu
* in menu enter pattern to filter/re-filter history
* select command line with arrows or enter number and press enter
* you can then edit the command line before execution

![demo](https://github.com/joknarf/redo/assets/10117818/cad55733-8ea0-450e-8115-b757d3b4ba9d)

## keys in menu

|key       | action                          |
|----------|---------------------------------|
|Down      | select nex item                 | 
|Up        | select prev item                |
|Right/End | select last item                |
|Left/Home | select first item               | 
|PgUp/Ctl-F| next page                       |
|PgDn/Ctl-B| previous page                   |
|Ctl-X/Esc | exit                            |
|Ctl-A     | use all screen to display menu  |
|Enter     | validate selected item          |
|Tab       | apply filter/new filter         |
|Del-F8    | Delete item from history file   |

* filter pattern can be applied entering text (ext regexp)
* selection can be done entering item number

## delete history commands

To delete command from current shell history and `$HISTFILE` use `redodel` command then chose command and press `Del or F8`.  

Using Del/F8 when using redo bind key (`Esc-/` `Ctl-R`) will not remove command from current shell history (line editing limitation), but the `$HISTFILE` will be purged from the command.  

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

* zsh on ubuntu 22 : in vi mode, to have `Esc-/` correctly binded, you need to put in `~/.zshenv`:
  ```
  skip_global_compinit=1
  ```
