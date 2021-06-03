---
title: /sites/
position_number: 1.1
type: get
description: Получить список бирж
parameters:
  - name:
    content:
content_markdown: |-
  Возвращает массив бирж.
left_code_blocks:
    title:
    language:
right_code_blocks:
  - code_block: |2-
      [
        {
            "id": "1",
            "name": "Fl.ru",
            "url": "https://fl.ru",
            "currency": "₽",
            "logo": "https://jobned.com/img/sites/fl-ru.png"
        },
        {
            "id": "2",
            "name": "Freelancehunt.com",
            "url": "https://freelancehunt.com",
            "currency": "₴",
            "logo": "https://jobned.com/img/sites/Freelancehunt.com.png"
        }
      ]
    title: Response
    language: json
  - code_block: |2-
      {
        "error": "Projects not found"
      }
    title: Error
    language: json
---