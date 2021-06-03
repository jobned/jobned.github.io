---
title: /projects/
position_number: 1.0
type: get
description: Получить список проектов
parameters:
  - name: sites
    content: Массив фильтрации
  - name: keywords
    content: Массив ключевых слов
  - name: start_from
    content: Получить проекты новее определенного id
content_markdown: |-
  Update an existing book in your collection.

  Этот вызов вернет максимум 100 проектов
  {: .info }
left_code_blocks:
  - code_block: |-
      {
        "sites": [
          {
            "id" : 1,
            "subcat" : [1,2],
          },
          {
            "id" : 2,
            "budgets" : {
            "budget" : 300,
            "budget_to" : 1500,
            "budget_per_hour" : 15,
            "budget_per_hour_to" : 2000
            }
          }
        ],
        "keywords" : ["html", "web"]
      }
    title: PHP
    language: php
right_code_blocks:
  - code_block: |2-
      [
        {
          "id": 1,
          "title": "The Hunger Games",
          "score": 4.5,
          "dateAdded": "12/12/2013"
        },
        {
          "id": 1,
          "title": "The Hunger Games",
          "score": 4.7,
          "dateAdded": "15/12/2013"
        },
      ]
    title: Response
    language: json
  - code_block: |2-
      {
        "error": true,
        "message": "Invalid offset"
      }
    title: Error
    language: json
---