---
title: /income/:id
position_number: 1.0
type: get
description: Beta
content_markdown: |-
  Customer income and employemnt information from a-meldinger (Skatteetaten)

  #### Payslip object parameters

  | Parameter | Description | Required? |
  |-------|--------|---------|
  | netto | netto consumer income  | Yes |
  | start_date | employemnt started at | Yes |
  | end_date | employment finished at | No |
  | laid_off | (array) laid-off periods within the last 6 months | No |
  | fixed_wage | deternimedd fixed wage level | Yes |
  | period_start | starting of the paysliip period | Yes |
  | period_end | ending of the paysliip period | Yes |
  | hourly_wage | set hourly rate | No |
  | income_rows | income positions included into the payslip | No |
  | income_rows.type | income row type. Available options: **fixed, vacation, other, hourly** | No |
  | income_rows.hours | number of hours, applicable for hourly paid jobs | No |
  | income_rows.amount | amount | No |
  | income_rows.period | income row period | No |
  | income_rows.benefit | benefit paid as. Available options: **kontantytelse, naturalytelse, utgiftsgodtgjoerelse** | No |
  | payslip_type | dominant payslip type, if several income rowss present. Available options: **fixed, other, hourly** | Yes |
  | total_payment | brutto payment, incl taxed | Yes |
  | position_amount | percent of the full-time position | No |
  | profession_code | position profession code | Yes |
  | employer_org_num | employer organizational number | Yes |
  | total_withholding_tax | amount of taxes paid | Yes |

  #### Employer object parameters

  | Parameter | Description | Required? |
  |-------|--------|---------|
  | name | organization name | Yes |
  | org_num | organizational ID/number | Yes |
  | public | (boolean) is public organization? | Yes |
  | current | (bollean) is employment active? | Yes |
  | start_date | emplyment started at | Yes |
  | end_date | emplument finished at | No |
  | employment | employemnt type. For the reference, please, see emplyment parameter above | Yes |
  | company_profile | company registered information at Enhetsregisteret | Yes |

  #### Employment parameter

  | Parameter | Description | Required? |
  |-------|--------|---------|
  | employment | overall employemnt type. Available options: **fixed_public, fixed_private, self_employed, substitute, hired_consultant**. NB: we're working on adding the following options as well: **retired, student, laid_off, household** | Yes |

left_code_blocks:
  - code_block: |-
      var settings = {
        "url": "https:/link.goscore.me/api/1.0/income/1",
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

      url = "https:/link.goscore.me/api/1.0/income/1"

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
        'url': 'https:/link.goscore.me/api/1.0/income/1',
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
      curl --location --request GET 'https:/link.goscore.me/api/1.0/income/1' \
      --header 'Content-Type: application/json' --header 'Authorization: Bearer <insert your token here>'
    title: Curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "income": {
          "payslips": [
            {
              "employer_org_num": "922707324",
              "fixed_wage": 22500.0,
              "hourly_wage": null,
              "total_withholding_tax": -4500.0,
              "total_payment": 22500.0,
              "netto": 18000.0,
              "payslip_type": "fixed",
              "period_start": "2020-03-01",
              "period_end": "2020-03-31",
              "income_rows": [
                {
                  "type": "fixed",
                  "hours": null,
                  "amount": 22500.0,
                  "period": "2020-03-01..2020-03-31",
                  "benefit": "kontantytelse"
                }
              ],
              "profession_code": "1317111",
              "position_amount": 60.0,
              "start_date": "2020-03-01",
              "end_date": null,
              "laid_off": [],
            }
          ],
          "employers": [
            {
              "name": "GOSCORE AS",
              "public": false,
              "current": true,
              "org_num": "922707324",
              "employment": "fixed_private",
              "start_date": "2020-03-01",
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
        "user_data_id": "5c6985db-980b-4dba-a58e-c11faa5ea052",
        "status": "done"
      }
    title: Response
    language: json
---
