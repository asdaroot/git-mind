# git-mind - репозиторий для сохранения структуры знаний по git
**Задача** - описать синтаксис команды и типовые кейсы, чтобы всегда были под рукой

## 1. Создание и инициализация репозитория

* `"Репозиторий (локальный)"` - папка на на локальном компьютере
* `"Репозиторий (удаленный)"` - репозиторий, н-р, в internet (github.com)

### 1.1 Создание локальной папки для файлов репозитория
```
$ ls
11232021_Linux_Mind.xmind
```
Папка создана, в нее добавлен 1 файл.

### 1.2 Инициализация локального репозитория
Выполняется командой `git init`
```
$ git init
Initialized empty Git repository in E:/1_Education/11232021_Linux_Mind/.git/
```
В папке локального репозитория создается папка `.git`

### 1.3 Проверка статуса
Выполняется командой `git status`
```
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        11232021_Linux_Mind.xmind

nothing added to commit but untracked files present (use "git add" to track)
```
Git говорит о том, что в папке репозитория есть файл, который не управляется системой контроля версий и
необходимо это файл (если это нужно) добавить под версионный контроль.

### 1.4 Добавление файла под версионный контроль
Выполняется командой `git add .`
```
$ git add .
```
`.` означает, что добавятся все файлы в текущей директории.
Можно указать конкретный файл.

### 1.5 Выполнить первый commit
Выполняется командой `git commit`
```
$ git commit -m "Add first version of linux-mind"
[master (root-commit) 0e6a420] Add first version of linux-mind
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 11232021_Linux_Mind.xmind

```
Ключ `-m` добавляет комментарий к commit.

### 1.6 Добавить удаленный репозиторий
Выполняется командой `git remote add origin`
```
$ git remote add origin https://github.com/asdaroot/linux-mind.git
```
### 1.7 Проверить, что ссылка на удаленный репозиторий добавилась
Выполняется командой `git remote -v`
```
$ git remote -v
origin  https://github.com/asdaroot/linux-mind.git (fetch)
origin  https://github.com/asdaroot/linux-mind.git (push)
```
### 1.8 Залить обновление в удаленный репозиторий
Выполняется командой `git push`
```
$ git push
fatal: The current branch master has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin master
```
Если выполнить изначально без доп. параметров, то ничего не получится.
Нужно указать `upstream` ветку.
```
$ git push -u origin master
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 80.05 KiB | 16.01 MiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/asdaroot/linux-mind.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
```
`-u` - указывает upstream


