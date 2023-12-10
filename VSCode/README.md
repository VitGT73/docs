# VS CODE CHEAT SHEET


**Телеметрия:**
telemetry = off

**Автосохранениe: **
Auto Save = afterDelay
Auto Save Delay = 15000

**Тримирование:**
Trim Final Newlines = true
Trim Trailing Whitespace = true

**Вставка пустой строки в конец файла:**
Insert Final Newline = true

Font size: 16

**Прячем главное меню (вызываем по ALT)**
Menu Bar Visibility = toggle

**Делаем меню менее ярким:**
Title Bar Style = custom

**Заменяем табы на пробелы: **
Render Whitespace = all
Tab size = 4
insert spaces = True

**Проверка правописания (после установки Code Spell Checker и Russian - Code Spell Checker)**
"cSpell.language": "en,ru",


автоактивация venv (не работает?)
Activate Env In Current Terminal = true


### Плагины:

Python (Microsoft)

Material Icon Theme


### Установка виртуального окружения:
```bash
python3 -m venv .venv
```
Тоже самое , но с обновлением pip
```
python3 -m venv .venv --upgrade-deps
```

### Активация виртуального окружения (перед началом работы в VS CODE):
```bash
source .venv/bin/activate
```
Деактивация
```bash
deactivate
```

### Сохранение зависимостей в файл
```bash
pip freeze > requirements.txt
```

```bash
pip install -r .\requirements.txt
```
