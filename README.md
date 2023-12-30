# redo
bash interactive history menu

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
* Ctl-R or Alt-X to access history menu
* or pattern + Ctl-R or Alt-X to filter and access history menu
* in menu enter pattern to filter history
* select command line with arrows or enter number and press enter
* you can then edit the command line before exection

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
|Ctl-X     | Exit                            |
|Ctl-A     | Use all screen to display menu  |
|Enter     | select item/exit or apply filter|

* filter pattern can be applied entering text (ext regexp)
* selection can be done entering item number