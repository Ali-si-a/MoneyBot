# MoneyBot
Этот Telegram-бот позволяет сравнивать курсы валют на 1 февраля и 28 февраля 2025 года с сайта ЦБ РФ. Бот использует Selenium для парсинга данных и Telebot для взаимодействия с пользователем.
Команды бота
# Необходимые библиотеки
- TelegramBotAPI
- Selenium
# Команды бота
- /start: запускает бота
- /list:	показывает список доступных валют
# Описание работы
- Бот использует библиотеку selenium для парсинга данных о курсах валют с сайта ЦБ РФ.
- При запросе курса он открывает сайт, выбирает соответствующие даты и получает курсы валют.
- Бот принимает трехбуквенный код валюты, сравнивает ее курсы на 1 и 28 февраля 2025 года и возвращает один из следующих смайликов:
😊 – если курс вырос
😞 – если курс упал
# Запуск кода
1. Скачайте или скопируйте код
2. Установите нужные библиотеки (requirements.txt)
3. Настройте Telegram-бот. Для этого создайте бота в Telegram и получить токен с помощью BotFather. Вставьте ваш токен в строку TOKEN = 'YOUR_BOT_TOKEN' в коде.
4. Запустите код
# Функции
- get_exchange_rates(): использует Selenium для получения курсов валют с сайта ЦБ России. Находит и нажимает элементы страницы, чтобы выбрать даты (1 и 28 февраля 2025 года). Извлекает значения валют и их курсы. Возвращает два словаря: первый — с курсами на 1 февраля, второй — с курсами на 28 февраля.
- start_message(message): отправляет приветственное сообщение пользователю. Описывает, как пользоваться ботом и какие команды доступны.
- list_currencies(message): получает курсы валют на 1 февраля. Отправляет пользователю список доступных валют.
- compare_exchange_rates(message): принимает код валюты (например, USD). Сравнивает курс валюты на 1 и 28 февраля. Отправляет эмодзи.
- handle_invalid_currency_length(message): проверяет длину введенного пользователем кода валюты. Если код не состоит из 3 символов, отправляет сообщение с инструкцией.
- основной блок (if __name__ == '__main__':): запускает бесконечный цикл опроса Telegram, чтобы бот реагировал на команды пользователей.
