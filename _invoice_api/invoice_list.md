---
title: /invoices/:id
position_number: 1.0
type: get
description: List all invoices (eFaktura) for a specified user consent by ID
parameters:
  - name: page
    content: (number) Page number. If not specified, first page is displayed.
  - name: per_page
    content: (number) Page limit. Define how many items to display.
parameters_title: Request params
content_markdown: |-
  By default shows all invoices for the User ID
  {: .info }

  List all invoices from all banks (if user consent is given)

left_code_blocks:
  - code_block: |-
      var settings = {
        "url": "https:/link.goscore.me/api/1.0/invoices/1",
        "method": "GET",
        "headers": {
          "Content-Type": "application/json"
        },
      };

      $.ajax(settings).done(function (response) {
        console.log(response);
      });
    title: jQuery
    language: javascript
  - code_block: |-
      import requests

      url = "https:/link.goscore.me/api/1.0/invoices/1"

      payload = {}
      headers = {
        'Content-Type': 'application/json'
      }

      response = requests.request("GET", url, headers=headers, data = payload)

      print(response.text.encode('utf8'))
    title: Python
    language: python
  - code_block: |-
      var request = require('request');

      var options = {
        'method': 'GET',
        'url': 'https:/link.goscore.me/api/1.0/invoices/1',
        'headers': {
          'Content-Type': 'application/json'
        }
      };

      request(options, function (error, response) {
        if (error) throw new Error(error);
        console.log(response.body);
      });
    title: Node.js
    language: javascript
  - code_block: |-
      curl --location --request GET 'https:/link.goscore.me/api/1.0/invoices/1' \
      --header 'Content-Type: application/json'
    title: Curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "invoices": [
          {
            "id": "8599002184",
            "creditor_name": "EnterCard Kredittkort",
            "creditor_org_number": 918713867,
            "efaktura_ref": "123456789",
            "type": "INVOICE",
            "status": "PROCESSED",
            "account": "14300642641",
            "kid": "110002444955",
            "org_number": 918713867,
            "amount": 463.0,
            "min_amount": 400.0,
            "credit_note_amount": null,
            "due_date": "2021-01-16",
            "overdue": true,
            "paid": true
          },
        ],
        "user_data_id": "1"
      }
    title: Response
    language: json
---
