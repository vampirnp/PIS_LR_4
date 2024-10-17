# ТЗ на страницу добавление в корзину и оплата товара front-end

## 1. Макеты страницы/функции/фичи
![Внесение данных](https://github.com/user-attachments/assets/d38441fe-5dd1-4c76-8456-86fed7ba9ad8)
![Оплата](https://github.com/user-attachments/assets/20b59c1e-d5d9-42b6-8299-810857a66228)



## 2. SEO

URL страницы: /purchase-ticket

Хлебные крошки: Главная > добавление товара в корзину  > Оформление заказа > Оплата заказа

## 3. JSON при инициализации


```json
{
   "ProductInfo": {
    "product_name": "Проводные наушники HyperX Cloud II KHX-HSCP-RD красный",
    "article": "12h12322",
    "rating": "4.6",
    "price": 13272
  },

  "clientInfo": {
    "firstName": "",
    "lastName": "",
    "middleName": "",
  },

  "contactInfo": {
    "email": "",
    "phone": ""
  },

  "delivery of goods": {
    "in the store": {
      "included": true,
    }
    "delivery to the address": {
      "included": false,
      "address": Ул.полевая д.45,
      "price": 6750
    }
  }

  "Payment method":{
    "SBP": {
        "included": true,
    },
    "SBERPay": {
        "included": false,
    },
    "Card": {
        "included": false,
    },
    "on the issue": {
        "included": false,
    }
  }
}
```

## 4. Маппинг данных

### 4.1 Форма оформления билета

Скриншот элемента: ![Изображение формы оплаты заказа](./[image](https://github.com/user-attachments/assets/794f40fa-e816-4408-b4c0-b3f77f4b6599))

Условие отображения: Всегда

Описание элемента:

| Элемент | Тип элемента | Поле из JSON | Примечание |
|---------|--------------|--------------|------------|
| Заголовок "Оплата заказа" | Текст | - | Статический текст |
| Заголовок "1 данные покупателя" | Текст | - | Статический текст |
| Поле "Фамилия" | Input, обязательное | clientInfo.lastName | - |
| Поле "Имя" | Input, обязательное | clientInfo.firstName | - |
| Поле "Отчество" | Input | clientInfo.middleName | Необязательное поле |
| Заголовок "2 Контактные данные" | Текст | - | Статический текст |
| Поле "Адрес электронной почты" | Input, обязательное | contactInfo.email | Валидация формата email |
| Поле "Контактный телефон" | Input, обязательное | contactInfo.phone | Маска ввода телефона |
| Заголовок "3 Способ получения" | Текст | - | Статический текст |
| Переключатель Способ получения | Toggle | delivery_of_goodsInfo.method | Выбор между в магазине и доставка по адрессу |
| Стоимость доставки | Текст | delivery_of_goodsInfo.price | "2000 ₽" |
| Поле "Адрес" | Input, обязательное | contactInfo.addres | Валидация формата addres |
 Заголовок "4 Способ оплаты" | Текст | - | Статический текст |
| Переключатель Способ оплаты | Toggle | Payment_methodInfo.method | Выбор оплаты между СБП СберПэй картой и наличкой в магазине|
| К оплате | Текст | price | Отображение итоговой стоимости |
| Кнопка "Оплатить" | Button | - | При нажатии переход к оплате |




