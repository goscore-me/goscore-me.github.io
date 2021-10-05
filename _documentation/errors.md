---
title: Error statuses
position_number: 7
parameters:
  - name:
    content:
content_markdown: |-
  | Status | Description |
  | --- | --- |
  | **BAD_REQUEST** | The goscore Link URL was incorrectly configured. |
  | **USER_CANCELLED** | The end user cancelled the flow. |
  | **INTERNAL_ERROR** | An internal error within the goscore service. Please contact <a href="mailto:support@goscore.me">support</a> for help. |
  | **TEMPORARY_ERROR** | A temporary error with the 3rd party services. Please try again. |

  All errors will return JSON in the following format:
left_code_blocks:
  - code_block: |-
      {
        "error": {
          "status": "BAD_REQUEST",
          "message": "The goscore Link URL was incorrectly configured."
        }
      }
    title:
    language: json
right_code_blocks:
  - code_block:
    title:
    language:
---
