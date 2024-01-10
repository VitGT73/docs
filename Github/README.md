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
