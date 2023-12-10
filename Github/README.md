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

