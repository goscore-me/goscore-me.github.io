---
title: Statuses
position_number: 2

description: |-
  Depending on your application settings the data collection process might have various statuses to identify the data quality and potential errors.

content_markdown: |-
  Check data collection statuses to get notification when the data is ready. Statuses are available with any information-related API call.

  If you've activated async data collection, please, check a status using any of the API, e.g. Loan or Personal.
  {: .warning }

  Please, note, that the process take some time and don't pull the information more than once in a second.
  {: .info }

  #### Statuses

  | Status | Description |
  |-------|--------|
  | new | Data collection request is created but the process hasn't been started |
  | in_progress | Data collection is in progress |
  | done | Full data is collected and available for use |
  | partially_done | Data is partially collected and available for retrieval |
  | error | Data wasn't collected because of an error |

left_code_blocks:
  - code_block:
    title:
    language:
right_code_blocks:
  - code_block:
    title:
    language:
---
