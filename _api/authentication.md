---
title: Authentication
position_number: 1
subtitle: /auth
subtitle_type: post
headers:
  - name: Client-ID
    content: client_id you've got from us
  - name: Secret-Key
    content: secret_key you've got from us
content_markdown: |-
  You need to be authenticated to make API calls. Please, reach out to us to get credentials to try APIs.

  You can generate a token using this request. When you get the token, access the relevant data with the consent code/ID saved you got after the gotrack process successfully completed.

  Please, keep in mind that token is valid for a limited time
  {: .info }

  Nothing will work unless you generate an API token
  {: .error}

left_code_blocks:
  - code_block: |2-
      $.ajax({
        url: 'https://link.goscore.me/api/1.0/auth',
        headers: {
            'Client-ID': '<client_id>',
            'Secret-Key': '<secret_key>',
            'Content-Type': 'application/json'
        },
        method: 'POST',
        dataType: 'json',
        success: function(data){
          console.log('success: ' + data);
        }
      });
    title: JQuery
    language: javascript
  - code_block: |2-
      curl -X POST -i -H "Content-Type: application/json" -H "Client-ID: <client_id>" -H "Secret-Key: <secret_key>" https://link.goscore.me/api/1.0/auth
    title: Curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "token": "eyJhbGciOiJIUzI1NiJ9.eyJhcHBfaWQiOjEsImV4cGlyZV9hdCI6MTYxMTA5NzA5NX0.v8Ayvhh-0zarI5eFj6uOvdyO40b7wQZP-uaO7S3ICb8",
        "expire_at": "01-19-2021 22:58"
      }
    title: Response
    language: json
---
