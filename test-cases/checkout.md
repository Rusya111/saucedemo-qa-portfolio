# Тест-кейсы: Оформление заказа (Checkout)

**Окружение:** Windows 11, Chrome 120 / Opera GX 132

| ID | Название | Приоритет | Тип | Предусловия | Шаги | Ожидаемый результат | Статус | Баг |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **TC-014** | Успешное оформление заказа | High | Позитивный | Авторизован. В корзине товар. Открыта корзина. | 1. Нажать Checkout.<br>2. Ввести First Name.<br>3. Ввести Last Name.<br>4. Ввести Zip Code.<br>5. Нажать Continue.<br>6. Нажать Finish. | 1. Переход на Overview.<br>2. Сумма (Item total) и налог (Tax) рассчитаны верно.<br>3. Переход на `/checkout-complete.html` с текстом "THANK YOU FOR YOUR ORDER". | **Passed** | - |
| **TC-015** | Оформление с пустым полем First Name | High | Негативный | Авторизован. В корзине товар. Открыт Checkout. | 1. Оставить поле First Name пустым.<br>2. Заполнить остальные поля.<br>3. Нажать Continue. | Ошибка: "First Name is required". | **Passed** | - |
| **TC-016** | Оформление с пустым полем Zip Code | High | Негативный | Авторизован. В корзине товар. Открыт Checkout. | 1. Заполнить First Name и Last Name.<br>2. Оставить Zip Code пустым.<br>3. Нажать Continue. | Ошибка: "Postal Code is required". | **Passed** | - |
| **TC-017** | Проверка итоговой суммы в Overview | Medium | Позитивный | Авторизован. В корзине 2 товара. Открыт Overview. | 1. Проверить Item total.<br>2. Проверить Tax.<br>3. Проверить Total. | 1. Item total = сумме цен товаров.<br>2. Tax рассчитан.<br>3. Total = Item total + Tax. | **Passed** | - |
