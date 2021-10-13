---
title: /vehicles/:id
position_number: 1.0
type: get
description: Beta
content_markdown: |-

  List all vehicles registered on the costumer name from Statens Vegvesen

  #### Vehicle information object parameters

  | Parameter | Description | Required? |
  |-------|--------|---------|
  | vehicle_information | (array) list of the registered vehicles with plate numbers. First value is a vehicle name, second - plate number | No |

  **NB!** Addional information is presented as is and isn't preprocessed. Please, consider that future changes in the schema will apply.

left_code_blocks:
  - code_block: |-
      var settings = {
        "url": "https:/link.goscore.me/api/1.0/vehicles/1",
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

      url = "https:/link.goscore.me/api/1.0/vehicles/1"

      payload = {}
      headers = {
        'Content-Type': 'application/json',
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
        'url': 'https:/link.goscore.me/api/1.0/vehicles/1',
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
      curl --location --request GET 'https:/link.goscore.me/api/1.0/vehicles/1' \
      --header 'Content-Type: application/json' --header 'Authorization: Bearer <insert your token here>'
    title: Curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "vehicles": {
          "first_name": "OLA",
          "middle_name": null,
          "last_name": "NORDMANN",
          "email": "ole.nordmann@gmail.com",
          "digital_mailbox": "DIGIPOST",
          "phone_number": "91234567",
          "birth_date": "1980-01-01",
          "vehicles": [
            ["DMC DeLorean (1967)", "OUTATIME"],
            ["Mercedes C180 Kompressor (2019)", "UR 10000"]
          ],
          "vehicles_detailed": [
              {
                "model_name": "Mercedes-Benz C300",
                "type": "personal_car",
                "type_code": "M1",
                "year": 2019,
                "plate_number": "UR 10000",
                "electric": false,
                "hybrid": false,
                "last_eu_control": "2019-11-08",
                "next_eu_control": "2021-11-08",
                "owned": true,
                "co_owned": false,
                "co_ownership": {
                  "name": "",
                  "address": null
                },
                "leased": false,
                "leasing": {
                  "name": "",
                  "address": null
                },
                "technical_details": {
                  "emissions": {
                    "environmental_class": "5L",
                    "engines": [
                      {
                        "co2": 139,
                        "nox": 135.8
                      }
                    ]
                  },
                  "engines": [
                    {
                      "type": "diesel",
                      "volume": 1968
                    }
                  ]
                }
              },
              {
                "model_name": "DeLorean",
                "type": "atv",
                "type_code": "MR",
                "year": 1967,
                "plate_number": "OUTATIME",
                "electric": false,
                "hybrid": false,
                "last_eu_control": null,
                "next_eu_control": null,
                "owned": true,
                "co_owned": false,
                "co_ownership": {
                  "name": "",
                  "address": null
                },
                "leased": false,
                "leasing": {
                  "name": "",
                  "address": null
                },
                "technical_details": {
                  "emissions": {
                    "environmental_class": null,
                    "engines": [
                      {
                        "co2": null,
                        "nox": null
                      }
                    ]
                  },
                  "engines": [
                    {
                      "type": "petrol",
                      "volume": 280
                    }
                  ]
                }
              }
            ]
        }
        "user_data_id": "5c6985db-980b-4dba-a58e-c11faa5ea052",
        "status": "done"
      }
    title: Response
    language: json
---
