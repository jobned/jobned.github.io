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
        "sites": [ // массивы фильтрации по биржам, категориям, бюджетам
          {
            "id" : 1, // id биржи
            "cat" : [1,2], // массив id картегорий
            "subcat" : [30,45], // массив id подкатегорий (Указывайте только подкатегории которые не входят в категории выше)
          },
          {
            "id" : 2, // id биржи
            "budgets" : { // массив фильтрации по бюджетам (ипользуется валюта биржи)
              "budget" : 300, // бюджет от
              "budget_to" : 1500, // бюджет до
              "budget_per_hour" : 15, // бюджет в час от
              "budget_per_hour_to" : 2000, // бюджет в час до
              "price_per_symbol" : 10 // бюджет за 1000 знаков (только для контентных бирж)
            }
          }
        ],
        "keywords" : ["html", "web"], // массив с включевыми словами или словосочетаниями
        "start_from" : 1622644515080 // получить проекты новее id
      }
    title: PHP
    language: php
right_code_blocks:
  - code_block: |2-
      [
        {
          "id": "1622729542595",
          "name": "MVP product using Betfair API",
          "text": "I&#039;m looking for someone who can build an MVP product which uses the Betfair API. <br /><br />\nThe product would be a web app that uses the Betfair API to obtain odds and then add to betslip in betfair to place the bets. <br /><br />\nFirst off I need to know if my idea is viable and can be achieved. Then to build an MVP to test it works.<br />",
          "budgets": {
            "budget": "1000",
            "budget_to": "0",
            "budget_per_hour": "0",
            "budget_per_hour_to": "0",
            "price_per_symbol": "0"
          },
          "website": {
            "id": "8",
            "name": "Upwork.com",
            "logo": "https://jobned.com/img/sites/upwork.png",
            "currency": "$",
            "category": {
                "id": "74",
                "name": "Web, Mobile & Software Dev",
                "subcategory": {
                    "id": "1188",
                    "name": "Full Stack Development"
                }
            }
          },
          "link": "https://jobned.com/link/aHR0cHM6Ly93d3cudXB3b3JrLmNvbS9qb2JzL01WUC1wcm9kdWN0LXVzaW5nLUJldGZhaXItQVBJXyU3RTAxYjkzNTJhNTUxZTJjZWVmZj9zb3VyY2U9cnNz",
          "timestamp": "1622729542"
        },
        {
          "id": "1622729477629",
          "name": "A product company is looking for a permanent React frontend developer",
          "text": "Codedo Limited is a provider of video streaming, transcoding, processing, live composition, storage and delivery solutions. We are looking for a React developer to extend our core team. Primary responsibility is the extension and continued development of a club sound-oriented product that we co-own, the product has ample venture backing and lots of traction.<br /><br />\nInitial tasks will consist of building out a React frontend for an Electron.js application (no Electron-specific skills needed), continuing with development of fan web interface.<br />",
          "budgets": {
            "budget": "0",
            "budget_to": "0",
            "budget_per_hour": "25",
            "budget_per_hour_to": "45",
            "price_per_symbol": "0"
          },
          "website": {
            "id": "8",
            "name": "Upwork.com",
            "logo": "https://jobned.com/img/sites/upwork.png",
            "currency": "$",
            "category": {
                "id": "74",
                "name": "Web, Mobile & Software Dev",
                "subcategory": {
                    "id": "1186",
                    "name": "Front-End Development"
                }
            }
          },
          "link": "https://jobned.com/link/aHR0cHM6Ly93d3cudXB3b3JrLmNvbS9qb2JzL3Byb2R1Y3QtY29tcGFueS1sb29raW5nLWZvci1wZXJtYW5lbnQtUmVhY3QtZnJvbnRlbmQtZGV2ZWxvcGVyXyU3RTAxMmRiYjdlYTg4OGQyY2FlOD9zb3VyY2U9cnNz",
          "timestamp": "1622729477"
        },
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