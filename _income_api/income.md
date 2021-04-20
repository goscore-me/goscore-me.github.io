---
title: /income/:id
position_number: 1.0
type: get
description: Beta
content_markdown: |-
  Customer income and employemnt information from a-meldinger (Skatteetaten)

left_code_blocks:
  - code_block: |-
      var settings = {
        "url": "https:/link.goscore.me/api/1.0/income/1",
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

      url = "https:/link.goscore.me/api/1.0/income/1"

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
        'url': 'https:/link.goscore.me/api/1.0/income/1',
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
      curl --location --request GET 'https:/link.goscore.me/api/1.0/income/1' \
      --header 'Content-Type: application/json'
    title: Curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "income": {
          "payslips": [
            {
              "netto": 18000.0,
              "end_date": null,
              "laid_off": [],
              "fixed_wage": 22500.0,
              "period_end": "2020-03-31",
              "start_date": "2020-03-01",
              "hourly_wage": null,
              "income_rows": [
                {
                  "type": "fixed",
                  "hours": null,
                  "amount": 22500.0,
                  "period": "2020-03-01..2020-03-31",
                  "benefit": "kontantytelse"
                }
              ],
              "payslip_type": "fixed",
              "period_start": "2020-03-01",
              "total_payment": 22500.0,
              "position_amount": 60.0,
              "profession_code": "1317111",
              "employer_org_num": "922707324",
              "total_withholding_tax": -4500.0
            }
          ],
          "employers": [
            {
              "name": "GOSCORE AS",
              "public": false,
              "current": true,
              "org_num": "922707324",
              "end_date": null,
              "payslips": [
                {
                  "netto": 18000.0,
                  "end_date": null,
                  "laid_off": [],
                  "fixed_wage": 22500.0,
                  "period_end": "2020-03-31",
                  "start_date": "2020-03-01",
                  "hourly_wage": null,
                  "income_rows": [
                    {
                      "type": "fixed",
                      "hours": null,
                      "amount": 22500.0,
                      "period": "2020-03-01..2020-03-31",
                      "benefit": "kontantytelse"
                    }
                  ],
                  "payslip_type": "fixed",
                  "period_start": "2020-03-01",
                  "total_payment": 22500.0,
                  "position_amount": 60.0,
                  "profession_code": "1317111",
                  "employer_org_num": "922707324",
                  "total_withholding_tax": -4500.0
                }
              ],
              "employment": "fixed_private",
              "start_date": "2020-03-01",
              "company_profile": {
                "id": "922707324",
                "raw": {
                  "navn": "GOSCORE AS",
                  "_links": {
                    "self": {
                      "href": "https://data.brreg.no/enhetsregisteret/api/enheter/922707324"
                    }
                  },
                  "konkurs": false,
                  "maalform": "Bokmål",
                  "antallAnsatte": 1,
                  "naeringskode1": {
                    "kode": "62.020",
                    "beskrivelse": "Konsulentvirksomhet tilknyttet informasjonsteknologi"
                  },
                  "stiftelsesdato": "2019-04-12",
                  "underAvvikling": false,
                  "organisasjonsform": {
                    "kode": "AS",
                    "_links": {
                      "self": {
                        "href": "https://data.brreg.no/enhetsregisteret/api/organisasjonsformer/AS"
                      }
                    },
                    "beskrivelse": "Aksjeselskap"
                  },
                  "forretningsadresse": {
                    "land": "Norge",
                    "adresse": [
                      "Blekenberg 30"
                    ],
                    "kommune": "BERGEN",
                    "landkode": "NO",
                    "poststed": "BERGEN",
                    "postnummer": "5055",
                    "kommunenummer": "4601"
                  },
                  "organisasjonsnummer": "922707324",
                  "institusjonellSektorkode": {
                    "kode": "2100",
                    "beskrivelse": "Private aksjeselskaper mv."
                  },
                  "registrertIMvaregisteret": false,
                  "sisteInnsendteAarsregnskap": "2019",
                  "registrertIForetaksregisteret": true,
                  "registrertIStiftelsesregisteret": false,
                  "registreringsdatoEnhetsregisteret": "2019-05-06",
                  "registrertIFrivillighetsregisteret": false,
                  "underTvangsavviklingEllerTvangsopplosning": false
                },
                "code": "2100",
                "name": "GOSCORE AS",
                "address": {
                  "city": "BERGEN",
                  "postal_code": "5055",
                  "street_address": "Blekenberg 30"
                },
                "org_form": "AS",
                "employees": 1,
                "founded_at": 1557093600,
                "country_code": "NO"
              }
            }
          ]
        },
        "employment": "fixed_private",
        "user_data_id": 38
      }
    title: Response
    language: json
---
