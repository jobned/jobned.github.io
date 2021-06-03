---
title: /categories/
position_number: 1.3
type: post
description: Получить список категорий
parameters:
  - name: sites
    content: Массив с id бирж
content_markdown: |-
  Возвращает массив категорий и подкатегорий.
left_code_blocks:
  - code_block: |-
        <?php
        $base = 'https://api.jobned.com/v1';
        $ch = curl_init($base . '/categories/');
        $token = 'as214SY@Jlsa<Safak';
        $data = array(
            "sites" => [1,2] // массив бирж
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
            "id": "21",
            "site_id": "2",
            "name": "Программирование",
            "subcategories": [
                {
                    "id": "243",
                    "site_id": "2",
                    "category_id": "21",
                    "name": "1C"
                },
                {
                    "id": "244",
                    "site_id": "2",
                    "category_id": "21",
                    "name": "Blockchain"
                },
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