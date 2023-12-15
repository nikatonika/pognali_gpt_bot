# Проект ассистента по поиску мероприятий в любом городе (Проектный практикум МФТИ 2023)

#### Автор проекта: Davron Ikhmatullaev
---

## Описание проекта:
Проект представляет собой телеграм-бота, который запоминает интересы пользователя и помогает ему найти интересные мероприятия для посещения в своем городе, найти интересные места для посещения во время путешествий, а также может придумать для компании друзей квесты по городу. 


## Функционал телеграм-бота:

1. Заполнение данных об пользователе:
    
    - в формате свободного разговора модель вычленяет из речи ключевые интересы и характеристики пользователя
    - модель отправляет полученную информацию в виде словаря
    - обновление данных пользователя в базе данных (postgres)
    
2. Поиск мероприятий для пользователя, исходя из его интересов, места проживания 
    - отправляется запрос в модель gpt-3.5-turbo-1106 по OpenAI API, c добавлением инструкции к промпту.
    - при обнаружении изменений в интересах пользователя модель выявит, какие обновления в интересах или характеристиках пользователя нужно внести
    - обновление данных пользователя в базе данных (postgres)
    - выдача ответа за запрос с учетом интересов и характеристик пользователя
3. Поиск интересных мест и заведений для посещения в любом городе:
    - пользователь выбирает город
    - отправляется запрос в модель gpt-3.5-turbo-1106 по OpenAI API, c добавлением инструкции к промпту.
4. Генерация квестов по городу.

---

## Как запустить бота у себя?! 

1. Создать телеграм бота в самом телеграме: @botfather
2. Создать аккаунт, если его нет, в open.ai
3. Сохранить токены от бота и open.ai API.
4. Cклонировать репозитарий к себе. (git clone git@github.com:fitlemon/pognali_gpt_bot.git)
5. Установить виртуальное окружение пайтон .venv в  корневой папке папке (Linux: python3 -m venv .venv Windows: python -m venv .venv)
6. Активировать виртуальное окружение .venv (Linux: source .venv/bin/activate Windows: .venv\Scripts\Activate.ps1)
7. Установить необходимые модули Python. (pip install -r requirements.txt)
8. Создать в корневой папке файлы: .env (хранение токенов) и db.json (хранение данных пользователей).
9. Запустить проект: (Linux: python3 main.py Windows: python main.py)

