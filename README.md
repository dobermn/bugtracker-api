# Bugtracker API

JSON HTTP API для работы с [багтрекером ВКонтакте](https://vk.com/bugs) с правами `read-only`.

Запросы отправляются на адрес https://bugtracker.cc/api/METHOD_NAME методом `POST` или `GET`.

Вместо `METHOD_NAME` необходимо указывать название метода.

#### Обязательные параметры для каждого запроса

| Параметр | Описание |
| -------- | ---------|
| access_token | Ключ доступа, полученный у чат-бота |
| v            | Номер версии                        |


## reports.getPreview

Список из превью последних 50 оставленных багрепортов

```json
[
    {
        "id": 132469,
        "reporter_id": 176481285,
        "time": 1561755780,
        "name": "Можно много раз отправлять жалобу на одного и того же пользователя.",
        "status": {
            "id": 0,
            "name": "Открыт"
        },
        "tags": [
            "Вопросы обо всём",
            "Неработающая функциональность",
            "Android",
            "6.0 Marshmallow",
            "UI",
            "VK Pay",
            "Сервисы"
        ]
    },
    {},
    {}
]
```

## reports.getById

Полный объект оставленного багрепорта

| Параметр | Описание |
| -------- | ---------|
| id       | ID багрепорта |

```json
{
    "id": 132469,
    "reporter_id": 176481285,
    "time": 1561755780,
    "name": "Можно много раз отправлять жалобу на одного и того же пользователя.",
    "description": {
        "steps": "1. Открываем сервис.\n2. Заходим в любой вопрос, в котором уже есть ответ.\n3. Жалуемся много раз на пользователя.",
        "actual_result": "Можно много раз жаловаться на пользователя, тем самым флудить жалобами.\nТа м одной жалобы от пользователя должно хватать.",
        "expected_result": "Можно отправить одну жалобу, если отправить больше жалоб за определённое время, то вылезет алерт с ошибкой."
    },
    "status": "Открыт",
    "priority": {
        "id": 2,
        "name": "Средний"
    },
    "issue": {
        "id": "3",
        "name": "Неработающая функциональность"
    },
    "product": {
        "id": 321,
        "name": "Вопросы обо всём",
        "version": []
    },
    "platforms": [
        {
            "id": "4",
            "name": "Android"
        }
    ],
    "systems": [
        {
            "id": "10007",
            "name": "6.0 Marshmallow"
        }
    ],
    "tags": [
        {
            "id": "187",
            "name": "UI"
        },
        {},
        {}
    ],
    "devices": [
        {
            "id": 514042506,
            "model": "Samsung SM-A500H",
            "marketing_name": "Samsung Galaxy A5",
            "platform": {
                "id": "4",
                "name": "Android",
                "version": {
                    "id": 514042506,
                    "name": "6.0 Marshmallow"
                }
            }
        }
    ],
    "attachments": [],
    "seen_by_moderator": 0,
    "reproduced_count": 0,
    "comments": []
}
```

## products.get

Список из превью всех публично доступных продуктов

```json
[
    {
        "id": 327,
        "name": "Погода",
        "join_status": "joined"
    },
    {},
    {}
]
```

## products.getById

Полный объект продукта

| Параметр | Описание |
| -------- | ---------|
| id       | ID продукта |

```json
{
    "id": 327,
    "name": "Погода",
    "description": "Сервис с прогнозом погоды: https:\/\/vk.com\/app7028481\n\nВерсию для ПК тестировать не нужно.",
    "photo": "https:\/\/pp.userapi.com\/c849128\/v849128436\/1c78ce\/CMvv5W6utkI.jpg?ava=1",
    "testing_completed": 0,
    "counters": {
        "members": 209,
        "bugs": 81,
        "bugs_open": 80,
        "bugs_in_process": 0,
        "bugs_fixed": 0
    },
    "versions": [
        {
            "id": 2073,
            "name": "1.0",
            "release_notes": "",
            "time": 1561642140,
            "counters": {
                "bugs": 81,
                "fixed_bugs": 0,
                "vulnerabilities": 0
            }
        }
    ]
}
```
