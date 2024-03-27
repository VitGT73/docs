# Сравнительная таблица Python vs JS/TS vs Java

### Типы данных

| **Action** |**Java**| **Python** | **JS / TS** |
|--------|----------|------------|-------------|
|Приведение к типу|
| - строки к целому: |  | `number = int(text)`|в десятичную систему: <br>`number = parseInt(text, 10)`<br>в шестнадцатеричную систему: <br> `number = parseInt(text, 16)`<br>и т.д.|
|Условное присваивание|
| - : | `value = positive === true? 'YES': 'NO'` | `value = 'YES' if positive == True else 'NO'` | `value = positive === true? 'YES': 'NO'` |
|Доступ к свойству<br> объекта по имени <br> свойства|
| - если название простое:|  | `obj.color = 'YELLOW'` | `obj.color = 'YELLOW'` |
| - если название сложное (составлено из двух строковых переменных: "title" + land_code): |  | `attribute = 'color'`<br> `value = getattr(obj, attribute, 'GREEN')`<br>`setattr(obj, attribute, value)`| `attribute = 'color';` <br> `value = obj[attribute] \|\| 'GREEN';`<br>`obj[attribute] = value;` |
| - : |  | `` | `` |
| - : |  | `` | `` |



| header 1 | header 2 | header 3 |
| ---      | ---      | ---      |
| cell 1   | cell 2   | cell 3   |
| cell 4 | cell 5 is longer | cell 6 is much longer than the others, but that's ok. It eventually wraps the text when the cell is too large for the display size. |
| cell 7   |          | cell 9   |
