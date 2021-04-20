---
title: /personal/:id
position_number: 1.0
type: get
description: Beta

content_markdown: |-
  Show personal customer data populated from the Folkeregisteret

left_code_blocks:
  - code_block: |-
      var settings = {
        "url": "https:/link.goscore.me/api/1.0/personal/1",
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

      url = "https:/link.goscore.me/api/1.0/personal/1"

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
        'url': 'https:/link.goscore.me/api/1.0/personal/1',
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
      curl --location --request GET 'https:/link.goscore.me/api/1.0/personal/1' \
      --header 'Content-Type: application/json'
    title: Curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "personal": {
          "sex": "man",
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
