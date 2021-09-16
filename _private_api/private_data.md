---
title: /personal/:id
position_number: 1.0
type: get
description: Beta

content_markdown: |-
  Show personal customer data populated from the Folkeregisteret

  #### Personal object parameters

  | Parameter | Description | Required? |
  |-------|--------|---------|
  | first_name | first name | Yes |
  | middle_name | middle name | No |
  | last_name | last name | Yes |
  | ssn | ID- or D-number | Yes |
  | status | DSF status | Yes |
  | birth_date | birth date | Yes |
  | address | full person's address | Yes |
  | moving_date | current address change date | Yes |
  | citizenships | (array) all confirmed citizenships | Yes |
  | norwegian_citizen | (boolean) does person have norwegian citizenship | Yes |
  | norwegian_resident | (boolean) is person a norwegian resident | Yes |
  | moved_to_norway_at | date of first moving in Norway | No |
  | registered_residence | (boolean) person's residency is registered in DSF | Yes |
  | sex | person's sex, Available options: **male, female** | Yes |
  | kids | number of kids under 18 | Yes |
  | marital_status | public marital status. Available options: **married, registered_partner, divorced, separated, widow, single** NB: we're working on adding **cohabitant** status as well | Yes |
  | living_conditions | current living conditions based on the registtered address. Available options: **rental, parents, own, housing_association** | Yes |
  | cohabitant | (boolean) has a registered partner | Yes |
  | additional_info | **BETA** (dict, hash) additional information directly from the register | No |

left_code_blocks:
  - code_block: |-
      var settings = {
        "url": "https:/link.goscore.me/api/1.0/personal/1",
        "method": "GET",
        "headers": {
          "Content-Type": "application/json",
          "Authorization": "Bearer <insert your token here>"
        },
      };

      $.ajax(settings).done(function (response) {
        console.log(response);
      });
    title: jQuery
    language: javascript
  - code_block: |-
      import requests

      url = "https:/link.goscore.me/api/1.0/personal/1"

      payload = {}
      headers = {
        'Content-Type': 'application/json'
        'Authorization': 'Bearer <insert your token here>'
      }

      response = requests.request("GET", url, headers=headers, data = payload)

      print(response.text.encode('utf8'))
    title: Python
    language: python
  - code_block: |-
      var request = require('request');

      var options = {
        'method': 'GET',
        'url': 'https:/link.goscore.me/api/1.0/personal/1',
        'headers': {
          'Content-Type': 'application/json',
          'Authorization': 'Bearer <insert your token here>'
        }
      };

      request(options, function (error, response) {
        if (error) throw new Error(error);
        console.log(response.body);
      });
    title: Node.js
    language: javascript
  - code_block: |-
      curl --location --request GET 'https:/link.goscore.me/api/1.0/personal/1' \
      --header 'Content-Type: application/json' --header 'Authorization: Bearer <insert your token here>'
    title: Curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "personal": {
          "first_name": "OLA",
          "middle_name": null,
          "last_name": "NORDMANN",
          "ssn": "01018012345",
          "status": "bosatt",
          "birth_date": "1980-01-01",
          "address": "KONGENS GATE 1, 0123 OSLO",
          "moving_date": "2016-06-01",
          "citizenships": [
              "Hviterussisk"
          ],
          "norwegian_citizen": true,
          "norwegian_resident": true,
          "moved_to_norway_at": null,
          "registered_residence": true,
          "sex": "male",
          "kids": 0,
          "marital_status": "single",
          "living_conditions": "rental",
          "cohabitant": false
        },
        "user_data_id": "5c6985db-980b-4dba-a58e-c11faa5ea052",
        "status": "done"
      }
    title: Response
    language: json
---
