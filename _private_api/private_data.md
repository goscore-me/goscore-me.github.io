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
  | sex | person's sex, Available options: **male, female** | Yes |
  | ssn | ID- or D-number | Yes |
  | kids | number of kids under 18 | Yes |
  | status | DSF status | Yes |
  | address | full person's address | Yes |
  | first_name | first name | Yes |
  | last_name | last name | Yes |
  | birth_date | birth date | Yes |
  | middle_name | middle name | No |
  | moving_date | current address change date | Yes |
  | citizenships | (array) all confirmed citizenships | Yes |
  | marital_status | public marital status. Available options: **married, registered_partner, divorced, separated, widow, single** NB: we're working on adding **cohabitant** status as well | Yes |
  | living_conditions | current living conditions based on the registtered address. Available options: **rental, parents, own, housing_association** | Yes |
  | norwegian_citizen | (boolean) does person have norwegian citizenship | Yes |
  | moved_to_norway_at | date of first moving in Norway | No |
  | norwegian_resident | (boolean) is person a norwegian resident | Yes |
  | registered_residence | (boolean) person's residency is registered in DSF | Yes |
  | additional_info | **BETA** (dict, hash) additional information directly from the register | Yes |

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
          "sex": "male",
          "ssn": "01018012345",
          "kids": 0,
          "status": "bosatt",
          "address": "BLEKENBERG 30, 5055 BERGEN",
          "last_name": "NORDMANN",
          "birth_date": "1980-01-01",
          "first_name": "OLE",
          "middle_name": null,
          "moving_date": "2019-06-01",
          "citizenships": [
            "Norsk"
          ],
          "marital_status": "single",
          "additional_info": {
            "cohabitant": false,
            "some_additional_info": {
              "konto": {
                "iban": "",
                "banknavn": "DNB ASA",
                "kontonummer": "12345678901",
                "bicEllerSwift": "",
                "erUtbetalingskort": false
              },
              "person": {
                "navn": "Ole Nordmann",
                "spraak": "Bokmål",
                "partsnummer": "123456789",
                "foedselsnummer": "01018012345"
              },
              "kontakt": {
                "epost": "ola.nordmann@gmail.com",
                "telefon": "91234567"
              },
              "adresser": [
                {
                  "land": "",
                  "type": "BOSTED",
                  "poststed": "OSLO",
                  "postnummer": "0153",
                  "adressetekst": "KONGENS GATE 1",
                  "registreringsdato": ""
                }
              ],
              "arbeidsgivere": [
                {
                  "arbeidsgiver": "KONGEN AS",
                  "hentetSkattekortDato": "2021-04-06"
                }
              ]
            }
          },
          "living_conditions": "own",
          "norwegian_citizen": true,
          "moved_to_norway_at": "1967-01-01",
          "norwegian_resident": true,
          "registered_residence": true
        },
        "user_data_id": "1"
      }
    title: Response
    language: json
---
