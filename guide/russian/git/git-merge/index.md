---
title: Git Merge
localeTitle: Git Merge
---
## Git Merge

Команда `git merge` объединяет любые изменения, внесенные в базу кода из любой отдельной ветки, в вашу текущую ветку.

Синтаксис команды следующий:

```shell
git merge BRANCH-NAME 
```

Например, если вы сейчас работаете в ветке с именем `dev` и хотели бы объединить любые новые изменения, которые были сделаны в ветке с именем `new-features`, вам нужно выполнить следующую команду:

```shell
git merge new-features 
```

**Обратите внимание:** если в вашей текущей ветке есть какие-либо незафиксированные изменения, Git не позволит вам сделать слияния, пока не будут зафиксированы все изменения в вашей текущей ветке. Чтобы решить эту задачу, вы можете:

*   Создать новую ветку и зафиксировать изменения

```shell
git checkout -b new-branch-name 
 git add . 
 git commit -m "<your commit message>" 
```

*   Скрыть изменения

```shell
git stash               # add them to the stash 
 git merge new-features  # do your merge 
 git stash pop           # get the changes back into your working tree 
```

*   Отменить все изменения

```shell
git reset --hard        # removes all pending changes 
```

## Конфликты во время слияния

Конфликты во время слияния - это когда вы совершаете фиксации на отдельных ветвях, которые изменяют одну и ту же строку конфликтующими способами. Поэтому Git не будет знать, какую версию файла сохранить

в результате появляется сообщение об ошибке:

CONFLICT (content): Конфликт в файле resumé.txt Ошибка автоматического слияния; исправьте конфликты и затем зафиксируйте результат.

В редакторе кода Git использует маркировки для указания HEAD (основной) версии файла и другой версии файла.

`<<<<<<< HEAD`

`>>>>>>> OTHER`

В редакторе кода удалите/обновите файлы, чтобы разрешить конфликт, и удалите специальные маркировки, включая имена HEAD и OTHER, сохраните файл, затем добавьте и зафиксируйте свои изменения.

Дополнительные сведения о команде `git merge` и всех доступных параметрах см. в [документации Git](https://git-scm.com/docs/git-merge) .
