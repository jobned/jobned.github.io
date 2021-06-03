---
title: /add_projects/
position_number: 1.4
type: post
description: Добавление проекта
parameters:
  - name: title
    content: Заголовок *
  - name: content
    content: Текст проекта *
  - name: site
    content: Id вашего сайта *
  - name: ctegory
    content: Id категории *
  - name: subcategory
    content: Id подкатегории
  - name: url
    content: Url страницы проекта *
content_markdown: |-
  Этот запрос добавляет проект в нашу базу<br />Все поля которые отмечены * обязательны!

  Для получения id сайта, категорий и подкатегорий - напишите нам и мы добавим вашу биржу к нам в базу
  {: .info }
left_code_blocks:
  - code_block: |-
      <?php
      $base = 'https://api.jobned.com/v1';
      $ch = curl_init($base . '/add_project/');
      $token = 'Your API key';
      $data = array(
        "title" => "Project title",
        "content" => "Project text",
        "site" => "1",
        "category" => "1",
        "subcategory" => "1",
        "url" => "https://jobned.com/projects/project/1/"
      );
      $data_string = json_encode($data);
      curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
      curl_setopt($ch, CURLOPT_FOLLOWLOCATION, 1);
      curl_setopt($ch, CURLOPT_CUSTOMREQUEST, "POST");
      curl_setopt($ch, CURLOPT_POSTFIELDS, $data_string);
      curl_setopt($ch, CURLOPT_HEADER, false);
      curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
      curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, false);
      $authorization = 'Authorization: Bearer ' . $token;
      curl_setopt($ch, CURLOPT_HTTPHEADER, array($authorization));
      $responce = curl_exec($ch);
      curl_close($ch);
      $responce = json_decode($responce, true);
      var_dump($responce);
      ?>
    title: Пример запроса php
    language: php
right_code_blocks:
  - code_block: |2-
      [
        {
          "id": "1622729542595",
          "name": "MVP product using Betfair API",
          "text": "I'm looking for someone who can build an MVP product which uses the Betfair API. The product would be a web app that uses the Betfair API to obtain odds and then add to betslip in betfair to place the bets. First off I need to know if my idea is viable and can be achieved. Then to build an MVP to test it works.",
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
          "text": "Codedo Limited is a provider of video streaming, transcoding, processing, live composition, storage and delivery solutions. We are looking for a React developer to extend our core team. Primary responsibility is the extension and continued development of a club sound-oriented product that we co-own, the product has ample venture backing and lots of traction. Initial tasks will consist of building out a React frontend for an Electron.js application (no Electron-specific skills needed), continuing with development of fan web interface.",
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