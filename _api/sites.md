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
  - code_block: |-
        <?php
        $base = 'https://jobned.com/api/v1';
        $ch = curl_init($base . '/sites/');
        $token = 'Your API key';
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
        curl_setopt($ch, CURLOPT_FOLLOWLOCATION, 1);
        curl_setopt($ch, CURLOPT_CUSTOMREQUEST, "GET");
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
        "error": "Wrong api key"
      }
    title: Error
    language: json
---