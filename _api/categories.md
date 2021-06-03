---
title: /categories/
position_number: 1.0
type: get
description: Получить список категорий
parameters:
  - name: sites
    content: Массив с id бирж
content_markdown: |-
  Возвращает массив категорий и подкатегорий.
left_code_blocks:
  - code_block: |-
      {
        "sites" : [1,2] // массив бирж
      }
    title: Пример массива тела запроса
    language: php
right_code_blocks:
  - code_block: |2-
      [
        {
            "id": "1",
            "site_id": "1",
            "name": "Разработка сайтов",
            "subcategories": [
                {
                    "id": "1",
                    "site_id": "1",
                    "category_id": "1",
                    "name": "Копирайтинг"
                },
                {
                    "id": "2",
                    "site_id": "1",
                    "category_id": "1",
                    "name": "Веб-программирование"
                }
            ]
        },
        {
            "id": "25",
            "site_id": "2",
            "name": "Продвижение",
            "subcategories": [
                {
                    "id": "299",
                    "site_id": "2",
                    "category_id": "23",
                    "name": "Настройка ПО/серверов"
                },
                {
                    "id": "300",
                    "site_id": "2",
                    "category_id": "23",
                    "name": "Обработка данных"
                }
            ]
        }
      ]
    title: Response
    language: json
  - code_block: |2-
      {
        "error": "Wrong api key"
      }
    title: Error
    language: json
---