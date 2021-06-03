---
title: Аутентификация
position_number: 2
parameters:
  - name:
    content:
content_markdown: |-
  Вам необходимо пройти аутентификацию для всех запросов API. Для получения API ключа напишите на почту <a href="mailto:partners@jobned.com">partners@jobned.com</a>.

  Добавьте ключ API ко всем запросам в качестве HTTP заголовка:
  Authorization: Bearer <ваш API ключ>

  Ничего не будет работать, если вы не укажете этот ключ API.
  {: .error}
left_code_blocks:
  - code_block:
    title:
    language:
right_code_blocks:
  - code_block: |2-
        $ch = curl_init('https://api.jobned.com/v1/sites/');
        $token = 'as214SY@Jlsa<Safak';
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
        curl_setopt($ch, CURLOPT_FOLLOWLOCATION, 1);
        curl_setopt($ch, CURLOPT_CUSTOMREQUEST, "GET"); 
        curl_setopt($ch, CURLOPT_HEADER, true);
        curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
        curl_setopt($ch,CURLOPT_SSL_VERIFYHOST, false);
        $authorization = 'Authorization: Bearer ' . $token;
        curl_setopt($ch, CURLOPT_HTTPHEADER, $authorization);
        $responce = curl_exec($ch);
        curl_close($ch);
        var_dump(json_decode($responce, true));
    title: Curl
    language: PHP
---