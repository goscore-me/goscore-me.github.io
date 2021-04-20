---
title: /vehicles/:id
position_number: 1.0
type: get
description: Beta
content_markdown: |-

  List all vehicles registered on the costumer name from Statens Vegvesen

left_code_blocks:
  - code_block: |-
      var settings = {
        "url": "https:/link.goscore.me/api/1.0/vehicles/1",
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

      url = "https:/link.goscore.me/api/1.0/vehicles/1"

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
        'url': 'https:/link.goscore.me/api/1.0/vehicles/1',
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
      curl --location --request GET 'https:/link.goscore.me/api/1.0/vehicles/1' \
      --header 'Content-Type: application/json'
    title: Curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "vehicles": {
          "vehicle_information": [
            ["DMC DeLorean", "OUTATIME"],
            ["Mercedes C180 Kompressor", "HB60019"],
          ],
          "epost": "ole.nordmann@gmail.com",
          "mobil": "91234567",
          "fornavn": "OLE",
          "malform": "Bokmal",
          "adresser": [
            {
              "land": {
                "landkode": "NOR",
                "landnavn": "NORGE"
              },
              "kommune": {
                "kommunenavn": "OSLO",
                "kommunenummer": "1000"
              },
              "poststed": {
                "poststed": "OSLO",
                "postnummer": "0153"
              },
              "adresse_id": "123123123",
              "adressetype": {
                "kode": "BOSTEDSADRESSE",
                "beskrivelse": "Bostedsadresse"
              },
              "adresselinje1": "KONGENS GATE 1",
              "adresselinje2": null,
              "adresselinje3": null
            }
          ],
          "kunde_id": "123123123",
          "etternavn": "NORDMANN",
          "mellomnavn": null,
          "fodselsdato": "1980-01-01T00:00:00.000+0100",
          "fodselsnummer": "01018012345",
          "spesialadresse": false,
          "digital_postkasse": {
            "reservert": false,
            "leverandor": "DIGIPOST"
          },
        }
        "user_data_id": "1"
      }
    title: Response
    language: json
---
