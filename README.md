# Пульт охраны банка

Это внутренний репозиторий для сотрудников банка «Сияние». Если вы попали в этот репозиторий случайно, то вы не сможете его запустить, т.к. у вас нет доступа к БД, но можете свободно использовать код вёрстки или посмотреть как реализованы запросы к БД.

Пульт охраны - это сайт, который можно подключить к удалённой базе данных с визитами и карточками пропуска сотрудников нашего банка.

### Как установить

В файле `settings.py` есть данные, которые надо убрать от общих глаз, поэтому мы используем переменные окружения. Для этого нам надо создать файл `.env` и можно сразу его записать в файл `.gitignore`. В него записываем переменные и значения. Например:

```
SECRET_KEY="ваше_значение"
```

Теперь нам надо передать эти значения в файл `settings.py` через библиотеку [environs](https://pypi.org/project/environs/). После установки библиотеки надо записать эти функции:

```
from environs import Env

env = Env()
env.read_env()
```

Передать переменные можно так:

```
SECRET_KEY = env("ваше_название_в_.env")
```

Версия Python `3.12`. Затем используйте `pip` (или `pip3`, есть есть конфликт с Python2) для установки зависимостей:
```
pip install -r requirements.txt
```

И вот вы уже можете запустить этот проект!

### Пример запуска
Запустить проект можно так:

```
python manage.py runserver 127.0.0.1:8000
```

## Цель проекта
Код написан в образовательных целях на онлайн-курсе для веб-разработчиков [dvmn.org](https://dvmn.org/).
