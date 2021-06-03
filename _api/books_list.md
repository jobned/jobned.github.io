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
  Update an existing book in your collection.<br />123

  Этот вызов вернет максимум 100 проектов
  {: .info }
left_code_blocks:
  - code_block: |-
      $.get("http://api.myapp.com/books/", { "token": "YOUR_APP_KEY"}, function(data) {
        alert(data);
      });
    title: jQuery
    language: javascript
  - code_block: |-
      r = requests.get("http://api.myapp.com/books/", token="YOUR_APP_KEY")
      print r.text
    title: Python
    language: python
  - code_block: |-
      var request = require("request");
      request("http://api.myapp.com/books?token=YOUR_APP_KEY", function (error, response, body) {
      if (!error && response.statusCode == 200) {
        console.log(body);
      }
    title: Node.js
    language: javascript
  - code_block: |-
      curl http://sampleapi.readme.com/orders?key=YOUR_APP_KEY
    title: Curl
    language: bash
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