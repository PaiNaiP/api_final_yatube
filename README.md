Финальный проект по API
Описание
Польза проекта в том, что он дает пользоваться функционалом приложения не посещая сайт.
Реализован функционал дающий возможность:
Подписываться на пользователя.
Просматривать, создавать новые, удалять и изменять посты.
Просматривать и создавать группы.
Комментировать, смотреть, удалять и обновлять комментарии.
Фильтровать по полям.
К API есть документация по адресу http://localhost:8000/redoc/
Установка
Клонируем репозиторий на локальную машину:

$ git clone https://github.com/netshy/api_final_yatube.git

Создаем виртуальное окружение:

$ python -m venv venv

Устанавливаем зависимости:

$ pip install -r requirements.txt

Создание и применение миграций:

$ python manage.py makemigrations и $ python manage.py migrate

Запускаем django сервер:

$ python manage.py runserver

Все готово к использованию API!

Примеры
Для формирования ответов и запросов будет использована программа Insomnia.

Получаем токен
Отправляем POST-запрос на адрес api/v1/token/ и передаем 2 поля в data.

username - указываем имя пользователя.
password - указываем пароль пользователя.
Примечание.

Токен refresh нужен, чтобы обновить текущий токен.
Токен access нужно сохранить и бережно хранить. Используется для аунтефикации пользователя.
Жизнь токена 1 год, в настройках можно изменить.


Создаем новый пост
Передаем POST-запрос, в заголовке указываем Authorization:Bearer <токен>

Обязательное поле: text


Фильтруем посты по номеру группы
Передаем GET-запрос, в params указываем поле group.


