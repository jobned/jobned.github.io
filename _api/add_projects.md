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
      
      {
        "success": "Ok"
      }
    title: Response
    language: json
  - code_block: |2-
      {
        "error": "Wrong api key"
      }
    title: Error
    language: json
---