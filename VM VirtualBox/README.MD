### Установка Ubuntu Server на VM VirtualBox

Ставим  на  2 Proc/4Gb RAM/20GB+ HDD остальное по умолчанию.
В процессе установки Server SSH - устанавливаем

#### Установка обновлений:
```
sudo apt update
sudo apt upgarde
```

Задаем пароль для root:
```
sudo -i
passwd
exit
```

Получаем локальный адрес
```hostname -I ```  (большая буква i )

Установка VS-CODE
```
sudo apt install ./<file>.deb
```

