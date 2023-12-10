### Установка и настройка Playwright для TypeScript

##### Проверяем версии пакетов node.js
```
node --version
npm --version
npx --version
```
##### Инсталляция playwright последней версии
```
npm init playwright@latest
```
##### Если необходимо установить зависимости
```
sudo npx playwright install-deps
```
(как я понял, это для workflow на github)

### Примеры часто используемых команд (внутри рабочей директории)

##### Запуск end-to-end тестов
```
npx playwright test
```
##### Запуск в интерактивном режиме (Starts the interactive UI mode)
```
npx playwright test --ui
```
##### Запуск в установленном в системе Google Chrome
```
npx playwright test --project=chromium
```
##### Запуск определенного файла
 ```
npx playwright test example
 ```
##### Запуск тестов в режиме отладки
```
npx playwright test --debug
```
##### Запуск генератора кода Codegen
```
npx playwright codegen
```
##### Посмотреть файл html c отчетом
```
npx playwright show-report
```

And check out the following files:
  - ./tests/example.spec.ts - Example end-to-end test
  - ./tests-examples/demo-todo-app.spec.ts - Demo Todo App end-to-end tests
  - ./playwright.config.ts - Playwright Test configuration


## Полезные настройки

### Внутри тестов

Использование storageState для всех тестов сразу или для каждого по отдельности. Перед всеми тестами:

```typescript
test.use({ storageState: '.auth/user.json'});
test.describe('my test - Profile - User', () => {
```
или только внутри нужных
```typescript
test.describe('my test - Profile - User', () => {
  test.use({ storageState: '.auth/user.json'});
  test ('my test', async({ page }) =>{
    ...
  });
});
```

Очистка куки перед запуском тестов, два варианта , второй временно может не работать
```typescript
test.use({ storageState: { cookies: [], origins: []}}); // doesn't share the logged in session
// test.use({ storageState: undefined }); // https://github.com/microsoft/playwright/issues/17396
```


Запускать тесты в последовательном режиме:
```typescript
test.describe.configure ({mode: 'serial'})

```
### В fixture
### В package.json
### В playwright-config.json


