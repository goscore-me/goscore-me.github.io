---
title: iFrame mode
position_number: 6
parameters:
  - name:
    content:
content_markdown: |-
  If you integrate gotrack directly in your application via an iframe (this mode is available for verified developers only), the result will be delivered as stringified object via [postMessage](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage) to the parent window.

left_code_blocks:
  - code_block:
    title:
    language:

right_code_blocks:
  - code_block: |2-
      {
          "type": "code",
          "code": "6915ab99857fec1e6f2f6c078",
      }
    title: Successful result
    language: json
  - code_block: |2-
      {
          "type": "error",
          "error": {
            "status": "BAD_REQUEST",
            "message": "Cancelled by user"
          },
      }
    title: Error
    language: json
---
