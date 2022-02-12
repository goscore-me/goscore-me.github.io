---
title: /loan_applications/:id
position_number: 1.0
type: get
description: Get a complete/combined loan application information. 
content_markdown: |-
  Only returns an information that's available with the actual api app scope.
  {: .info }
  
  Collect a complete loan application dataset in the same format as a separated API responses below.
  Check the APIs below for a detailed descriptions of the data models.

  
left_code_blocks:
  - code_block: |-
      $.ajax({
        url: 'https://link.goscore.me/api/1.0/loan_applications/1',
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
      r = requests.get("https://link.goscore.me/api/1.0/loan_applications/1", headers={ "Authorization": "Bearer <token>", "Content-Type": "application/json" })
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

      request({ url: "https://link.goscore.me/api/1.0/loan_applications/1", headers: { "Authorization": "Bearer <token>", "Content-Type": "application/json" }}, callback)
    title: Node.js
    language: javascript
  - code_block: |-
      curl -i -H "Content-Type: application/json" -H "Authorization: Bearer <token>" https://link.goscore.me/api/1.0/loan_applications/1
    title: Curl
    language: bash
right_code_blocks:
  - code_block: |2-
      {
        "vehicles": {
        ...
        },
        "loans": [
        ...
        ],
        "personal": {
        ...
        },
        "income": {
        ...
        },
        "employment": "",
        "student_loan": {
        ...
        },
        "tax_documents": {
          "personal": {
            "tax_reports": [
              "data:application/pdf;base64,...",
              "data:application/pdf;base64,...",
            ],
            "detailed_shares_data": [
              "data:application/pdf;base64,...",
            ],
            "business_assignment": [
              "data:application/pdf;base64,...",
            ]
          },
          "corporate": {
            "<org_number>": {
              "latest_tax_report": [
                "data:application/pdf;base64,..."
              ],
              "latest_annual_report": [
                "data:application/pdf;base64,..."
              ],
              "latest_shareholders_report": [
                "data:application/pdf;base64,..."
              ]
            }
          }
        },
        "user_data_id": "36339d62-956c-4997-9cc0-3d6862c850da",
        "status": "done"
      }
    title: Response
    language: json
---
