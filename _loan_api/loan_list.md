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

  Lists all the unsecured loans and student loan from Lånekassen collected for the selected User ID. Read more above about how to get a valid token.

  #### Loan object parameters

  | Parameter | Description | Required? |
  |-------|--------|---------|
  | creditor_name | name of the financial institution | Yes |
  | creditor_org_number | company ID from the public register | Yes |
  | has_co_borrower | (boolean) is this loan is shared with anyone else, has a co-borrower | Yes |
  | co_borrower | (boolean) is current custoner a co-borrower for another person | Yes |
  | credit_limit | credit car limit | No |
  | loan_amount | original loan amount | No |
  | balance | current loan balance | No |
  | charges | monthly payment charges/fees | No |
  | charge_period | perios applicable for chargees. Should be always "MONTHLY" if present | No |
  | type | loan type. Could be one of the following options only: **'credit_card', 'consumner_loan', 'charge_card'** | Yes |
  | nominal_rate | nominal interest rate | No |
  | current_balance | current loan balance, amount owned to the financial institution | Yes |
  | balance_with_interest | balance used to calculate interest rate | Yes |
  | balance_without_interest | balance with 0% nominal interest rate | Yes |
  | terms | number of months for consumer loan | No |
  | kid | unique identificator of payer for monthly payments | No |
  | account | financial institution account number used to transfer money to | No |

  #### Student loan object parameters
  If the applicant isn't customer at Lånekassen (never applied to get a loan), the response would be a blank hash `"student_loan": {}`
  {: .info }

  | Parameter | Description | Required? |
  |-------|--------|---------|
  | balance | current loan balance | No |
  | fees | current fees calculated | No |
  | charges | additional fees charged | No |
  | interest | interest calculated (in kr) | No |
  | status | data collection status. If data is available, it returns `ok`, and if data isn't available at Lånekassen anymore, you get `unavailable` | No |
  | status_reason | Only if data isn't available. The following statuses could be returned: `moved_to_debt_collection`, if the loan was permanently transferred to Statens Innkrevingssentral, `terminated` if loan is discarded, `debt_settlement` if debt settlement process initiated, or `unrecognized` if the reason isn't available | No |

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
            "terms": 59,
            "kid": "012345677899",
            "account": "42024603940"
          },
          {
            "creditor_name": "RESURS BANK AB",
            "creditor_org_number": 984150865,
            "has_co_borrower": false,
            "co_borrower": false,
            "credit_limit": null,
            "loan_amount": 10176.63,
            "balance": 9842.06,
            "charges": 45.0,
            "charge_period": "monthly",
            "type": "consumner_loan",
            "nominal_rate": 6.17,
            "current_balance": 9842.06,
            "balance_with_interest": 0.0,
            "balance_without_interest": 0.0,
            "terms": 0.48,
            "kid": null,
            "account": '42026512345'
          },
          {
            "creditor_name": "BB - TF BANK NORGE",
            "creditor_org_number": 923194592,
            "has_co_borrower": false,
            "co_borrower": false,
            "credit_limit": 30000.0,
            "loan_amount": null,
            "balance": null,
            "charges": 0.0,
            "charge_period": "monthly",
            "type": "credit_card",
            "nominal_rate": 19.9,
            "current_balance": 0.0,
            "balance_with_interest": 0.0,
            "balance_without_interest": 0.0,
            "terms": null,
            "kid": null,
            "account": null
          },
          {
            "creditor_name": "AMERICAN EXPRESS EUROPE S A",
            "creditor_org_number": 920854346,
            "has_co_borrower": false,
            "co_borrower": false,
            "credit_limit": null,
            "loan_amount": null,
            "balance": null,
            "charges": null,
            "charge_period": null,
            "type": "charge_card",
            "nominal_rate": null,
            "current_balance": 29118.06,
            "balance_with_interest": 0.0,
            "balance_without_interest": 29118.06,
            "terms": null,
            "kid": null,
            "account": null
          }
        ],
        "student_loan": {
          "balance":367914.67,
          "fees":7910.0,
          "charges":0.0,
          "interest":39456.67,
          "status":"ok"
        },
        "user_data_id": "5c6985db-980b-4dba-a58e-c11faa5ea052",
        "status": "done"
      }
    title: Response
    language: json
---
