# redo
bash interactive history menu  
replacement for bash `Ctl-R` and `Esc+/` to search in history and re-execute/re-edit commands.

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

![redo](https://github.com/joknarf/redo/assets/10117818/d09f0b51-d356-462b-8738-e9b05bb68ba5)

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

* filter pattern can be applied entering text (ext regexp)
* selection can be done entering item number
