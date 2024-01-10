<h1 align="center">"GigHub HOW TO"</h1>

### Создание ключа ssh

``` bash
ssh-keygen -t rsa -b 4096 -C "tvit@mail.ru"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
cat ~/.ssh/id_rsa.pub
```
* id_rsa - файл с ключом
* id_rsa.pub - файл с публичным ключом


### Первичная настройка github
Подключаемся по созданному ключу
```bash
ssh -T git@github.com
```

Задаем мои параметры:
```bash
git config --global user.email "tvit@mail.ru"
git config --global user.name "VitGT"
```




Создаем новый проект на своем компе:

```bash
mkdir learn_branches && cd learn_branches && git init # создали новый репозиторий
touch README.md # создали файл
git add . # команда git add с флагом-точкой подготовит к сохранению текущую папку; вместо этого можно вызвать git add --all
git commit -m "Выполнить первый коммит"
git branch -m master main
git push -u origin main
```



Клонируем этот репозиторий на локальную машину
```bash
git clone git@github.com:VitGT73/VitGT73.git
```

### Первый коммит
```bash
git add --all
git commit -am "first commit"
git push
```

Изменить commit (например добавить файлы) без исправления комментария
```bash
git commit --amend --no-edit
```

Изменить сообщение коммита:
```bash
git commit --amend -m "Новое сообщение"
```

«Откатить» изменения, которые не попали ни в staging, ни в коммит, —
```bash
git restore <file>
```

Команда ```git restore --staged <file>``` переведёт файл из staged обратно в modified или untracked.
Команда ```git reset --hard <commit hash>``` «откатит» историю до коммита с хешем <hash>. Более поздние коммиты потеряются!
Команда ```git restore <file>``` «откатит» изменения в файле до последней сохранённой (в коммите или в staging) версии.


## Работа с ветками

Задаем название главной ветки по умолчанию:
```bash
git config --global init.defaultBranch main
```

Создаем новую ветку и сразу переключаемся на нее
```bash
git checkout -b <название_ветки>
```
или
```bash
git branch %название-ветки% && git checkout %название-ветки%
```
Сравнение веток:
```bash
git diff main feature/diff
```
или сравнение с определенным коммитом (получить список коммитов: ```git log --oneline```):
```bash
git diff main 2ea56ab
```
Объединить ветки:
```bash
git branch # проверяем местоположение
git checkout main # если не в основной, переходим в неё
git merge feature/diff

```



Удалить ветку:
```bash
git branch # проверяем местоположение
git checkout main # если не в основной, переходим в неё

git branch -d feature/diff # удаляем поглощаемую ветку (безопасный вариант - удаляет ветку только, если все коммиты добавлены в main )
```
```
git branch -D feature/diff # удаляет поглощаемую ветку в любом случае
```
 Удаление локальной ветки через Git не удаляет ветку на GitHub!


#### Перед созданием pull-request выполняем:

```bash
git checkout main # перешли в main
git pull # подтянули новые изменения в main
git checkout my-branch # вернулись в рабочую ветку my-branch
git merge main # влили main в новую ветку my-branch
git push -u origin my-branch # отправили ветку my-branch в удалённый репозиторий
```

Удалить привязку к чужому репозиторию
```bash
git remote rm origin
```



## Шпаргалка. Работа с ветками

### Клонирование чужого репозитория
```git clone git@github.com:YandexPraktikum/first-project.git```
 (от англ. clone, «клон», «копия») — склонируй репозиторий с URL ```first-project.git``` из аккаунта ```YandexPraktikum``` на мой локальный компьютер.
### Создание веток

```git branch feature/the-finest-branch``` (от англ. branch, «ветка») — создай ветку от текущей с названием ```feature/the-finest-branch```;

```git checkout -b feature/the-finest-branch``` — создай ветку ```feature/the-finest-branch``` и сразу переключись на неё.

### Навигация по веткам

```git branch``` (от англ. branch, «ветка») — покажи, какие есть ветки в репозитории и в какой из них я нахожусь (текущая ветка будет отмечена символом ```*```);

```git branch -a``` — покажи все известные ветки, как локальные (в локальном репозитории), так и удалённые (в ```origin```, или на GitHub).

```git checkout feature/br``` — переключись на ветку ```feature/br```.

### Сравнение веток

```git diff main HEAD``` (от англ. difference, «отличие», «разница») — покажи разницу между веткой ```main``` и указателем на ```HEAD```;

```git diff HEAD~2 HEAD``` — покажи разницу между тем коммитом, который был два коммита назад, и текущим.

### Удаление веток

```git branch -d br-name``` — удали ветку ```br-name```, но только если она является частью ```main```;

```git branch -D br-name``` — удали ветку ```br-name```, даже если она не объединена с ```main```.

### Слияние веток

```git merge main``` (от англ. merge, «сливать», «поглощать») — объедини ветку ```main``` с текущей активной веткой.


### Работа с удалённым репозиторием

```git push -u origin my-branch``` (от англ. push, «толкнуть», «протолкнуть») — отправь новую ветку my-branch в удалённый репозиторий и свяжи локальную ветку с удалённой, чтобы при дополнительных коммитах можно было писать просто ```git push``` без ```-u```;

```git push my-branch``` — отправь дополнительные изменения в ветку ```my-branch```, которая уже существует в удалённом репозитории;

```git pull``` (от англ. pull, «вытянуть») — подтяни изменения текущей ветки из удалённого репозитория.
