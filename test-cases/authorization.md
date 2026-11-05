# Тест-кейсы: Авторизация

**Окружение:** Windows 11, Chrome 120 / Opera GX 132  
**Тестовые данные:** Файл `sources/test-cases.xlsx` (лист "Тестовые данные")

| ID | Название | Приоритет | Тип | Предусловия | Шаги | Ожидаемый результат | Статус | Баг |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **TC-001** | Вход с валидными данными | High | Позитивный | Открыта страница логина | 1. Ввести логин `standard_user`.<br>2. Ввести пароль `secret_sauce`.<br>3. Нажать Login. | Редирект на `/inventory.html`. | **Passed** | - |
| **TC-002** | Вход с валидным логином и невалидным паролем | High | Негативный | Открыта страница логина | 1. Ввести логин `standard_user`.<br>2. Ввести пароль `invalid_pass`.<br>3. Нажать Login. | Ошибка: "Username and password do not match any user in this service". | **Passed** | - |
| **TC-003** | Вход с невалидным логином и валидным паролем | High | Негативный | Открыта страница логина | 1. Ввести логин `not_user`.<br>2. Ввести пароль `secret_sauce`.<br>3. Нажать Login. | Ошибка: "Username and password do not match any user in this service". | **Passed** | - |
| **TC-004** | Вход заблокированного пользователя | High | Негативный | Открыта страница логина | 1. Ввести логин `locked_out_user`.<br>2. Ввести пароль `secret_sauce`.<br>3. Нажать Login. | Ошибка блокировки: "Epic sadface: Sorry, this user has been locked out." | **Passed** | - |
| **TC-005** | Вход с пустым полем "Username" | High | Негативный | Открыта страница логина | 1. Оставить поле логина пустым.<br>2. Ввести пароль `secret_sauce`.<br>3. Нажать Login. | Ошибка: "Username is required". | **Passed** | - |
| **TC-006** | Вход с пустым полем "Password" | High | Негативный | Открыта страница логина | 1. Ввести логин `standard_user`.<br>2. Оставить поле пароля пустым.<br>3. Нажать Login. | Ошибка: "Password is required". | **Passed** | - |
