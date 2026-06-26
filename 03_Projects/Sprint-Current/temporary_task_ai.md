---
tags:
  - project
  - ideas
  - ai
  - scratchpad
---
I have been working on collecting regex rules from specific labeling standards, such as IEC 62424 and ISO 10628. These rules are currently structured in the following files:

`data\common\labeling_standards\regex_and_plain_language\IEC_62424_regex_rules_structured.json`

`data\common\labeling_standards\regex_and_plain_language\ISO_10628_regex_rules_structured.json`

There is also a spike implementation that takes these structured rules and runs them against specific `pid.json` files. The implementation can be found here:

`src\spikes\regex_tag_extraction\demo\README.md`

At the moment, the regex tag matching scores for the two BASF files are quite low:

Dataset
Precision
Recall
F1

LU_V153_V05_0101_T3
11.70%
23.81%
15.69%

LU_V153_V05_0105_T4
11.11%
22.18%
14.81%

For the next task, I want to improve these scores specifically for the BASF files.

The goal is not to extract generic rules from standards such as IEC 62424 or ISO 10628. Instead, I want you to inspect the ground-truth `pid.json` files for the two BASF datasets and thoroughly understand which texts are associated with which symbols.

The relevant files are:

`data\labelled_data\LU_V153_V05_0105_T4\pid.json`

`data\labelled_data\LU_V153_V05_0101_T3\pid.json`

Based on this ground truth, please create a custom BASF-specific regex rule set in the same style and structure as the existing instruction JSON files:

`data\common\labeling_standards\regex_and_plain_language\IEC_62424_regex_rules_structured.json`

`data\common\labeling_standards\regex_and_plain_language\ISO_10628_regex_rules_structured.json`

For example, the rules should follow this format:

```
{
  "id": "b13120ed-eae3-45ab-8c65-888082ded134",
  "classKey": "column",
  "ruleType": "TEXT",
  "ruleCategory": "TAG_IDENTIFICATION",
  "textRole": "TAG",
  "englishRule": "Column/tower — letter K + 3-4 digit number + optional suffix",
  "classificationMode": "REGEX_ONLY",
  "sourceStandard": "ISO 10628 (letter codes per DIN 28004)",
  "lookupTable": "",
  "regex": "^K[-\\u2010\\u2013]?\\d{3,4}[A-Z]?$",
  "textSplitRegex": "^([A-Z])([-\\u2010\\u2013]?)(\\d{3,4})([A-Z]?)$"
}
```

Please write the new custom BASF rules to:

`data\common\labeling_standards\regex_and_plain_language\custom\BASF\basf_custom_regex_rules_structured.json`

These BASF-specific rules will later be layered on top of the existing IEC 62424 and ISO 10628 rule sets, with the goal of improving precision, recall, and F1 score for the two BASF datasets.

For this custom rule set, you may be very specific. For example, if the BASF ground truth shows that a certain valve type, pump type, vessel, tag format, or equipment class follows a specific pattern, create a targeted regex rule for that class.

Please proceed step by step:

1. Inspect both BASF `pid.json` files.
2. Identify all text-to-symbol associations from the ground truth.
3. Group the observed tag/text patterns by symbol class.
4. Compare these patterns with the existing IEC 62424 and ISO 10628 regex rules.
5. Derive additional BASF-specific regex rules only where they are useful.
6. Write the rules into the BASF custom JSON file.

Please be thorough but concise. If anything is unclear, ask questions before making assumptions. If a decision needs approval, explain the options clearly and ask for approval before proceeding.