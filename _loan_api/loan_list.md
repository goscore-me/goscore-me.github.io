---
title: /loans/:id
position_number: 1.0
type: get
description: List all loans for a specified user consent by ID
parameters:
  - name: page
    content: (number) Page number. If not specified, first page is displayed.
  - name: per_page
    content: (number) Page limit. Define how many items to display.
parameters_title: Request params
content_markdown: |-
  By default shows all loans for the User ID
  {: .info }

  Lists all the unsecured loans collected for the selected User ID. Read more above about how to get a valid token.
left_code_blocks:
  - code_block: |-
      $.ajax({
        url: 'https://link.goscore.me/api/1.0/loans/1',
        data: {
          page: 2,
          per_page: 50
        }
        headers: {
          'Authorization': 'Bearer <token>',
          'Content-Type': 'application/json'
        },
        method: 'GET',
        dataType: 'json',
        success: function(data){
          console.log('success: ' + data);
        }
      });
    title: jQuery
    language: javascript
  - code_block: |-
      r = requests.get("https://link.goscore.me/api/1.0/loans/1", headers={ "Authorization": "Bearer <token>", "Content-Type": "application/json" })
      print r.text
    title: Python
    language: python
  - code_block: |-
      var request = require("request");

      function callback (error, response, body) {
        if (!error && response.statusCode == 200) {
          console.log(body);
        }
      }

      request({ url: "https://link.goscore.me/api/1.0/loans/1", qs: { page: 2, per_page: 50 }, headers: { "Authorization": "Bearer <token>", "Content-Type": "application/json" }}, callback)
    title: Node.js
    language: javascript
  - code_block: |-
      curl -i -H "Content-Type: application/json" -H "Authorization: Bearer <token>" https://link.goscore.me/api/1.0/loans/1?page=2&per_page=50&active=true
    title: Curl
    language: bash
right_code_blocks:
  - code_block: |2-
      {
        "loans": [
          {
            "creditor_name": "SPAREBANK 1 KREDITT AS",
            "creditor_org_number": 975966453,
            "has_co_borrower": false,
            "co_borrower": false,
            "credit_limit": 35000.0,
            "loan_amount": null,
            "balance": null,
            "charges": 0.0,
            "charge_period": "monthly",
            "type": "credit_card",
            "nominal_rate": 21.62,
            "current_balance": 349.0,
            "balance_with_interest": 0.0,
            "balance_without_interest": 349.0,
            "kid": "016470713880",
            "account": "42024603940"
          }
        ],
        "user_data_id": 1
      }
    title: Response
    language: json
---
