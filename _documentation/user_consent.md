---
title: Collect Data with gotrack
position_number: 4
parameters:
  - name:
    content:
content_markdown: |-
  API customers can get access to the goscore API by using the gotrack web-app, which uses industry standard OAuth2 authentication methods for transparent and secure access to user data.

  #### This is how gotrack works:

  1. User is taken to [https://theia.goscore.me]()
  2. User select the authentication method, e.g. BankID
  3. An user identificator (ID) (used to retrieve data) is sent back to the application
  4. With the ID together with API access_token, your application can fetch the user's data from the goscore API.

  #### Initialization parameters

  You need an authorization link to be able to send users to gotrack and this link can be customized with different parameters.

  | Parameter | Description | Required? |
  |-------|--------|---------|
  | client_id | you unique client ID | Yes |
  | scope | collected data following the user consent, comma-separated. E.g. unsecured_loans,student_loan,e_invoices. All allowed options: **vehicles, unsecured_loans, info, income, student_loan, e_invoices** | Yes |
  | locale | language selection. Available languages: **en, nb** | No |
  | iframe | on-page integration | No |
  | callback_uri | redirect URL. This is the path that will receive the code. | No |
  | test | indicate if test flow is enabled (static data) | No |
  | styles_uri | URL for your custom CSS file. It overwrites standard styles | No |

  #### Response

  When the gotrack process is done, you will get a response with the result. This will either be a success, error or a status (status available in iframe mode only) and will be delivered to the specified callback_uri. Based on your integration of gotrack, the response will be delivered using on of the following means:

  * Redirect integration - the response will be sent using query parameters to the specified callback_uri.
  * Iframe integration - the response will be sent to the parent window using a postMessage notification.

left_code_blocks:
  - code_block:
    title:
    language:
right_code_blocks:
  - code_block:
    title:
    language:
---
