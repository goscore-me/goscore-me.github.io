---
title: Redirect mode
position_number: 5
parameters:
  - name:
    content:
content_markdown: |-
  In this case the user of your application is redirected to your gotrack URL. Once the gotrack flow is completed, the user will be redirected to your specified **callback_uri**, e.g. *https://my-doamin/oauth/callback*

left_code_blocks:
  - code_block:
    title:
    language:

right_code_blocks:
  - code_block: |2-
      https://my-doamin/oauth/callback?code=123
    title: Successful result
    language: bash
  - code_block: |2-
      https://my-doamin/oauth/callback?error=cancelled%20by%20user
    title: Error
    language: bash
---
