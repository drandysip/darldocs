Class QuestionSetProxy
===

The set of questions or responses and status info.

# Properties

## CanUnwind
boolean

Indicates that the user can unwind a previous set of answers


## Complete
boolean

True if questionnaire is completely satisfied.


## ieToken
GUID represented as string

Identifies this questionnaire run


## Language
string

2 character iso of the language requested


## PercentComplete
double

Percentage complete, 0-100


## Preamble
string

text displayed before form


## QuestionHeader
string

text displayed before questions


## questions
List&lt;[QuestionProxy](QuestionProxy)&gt;

Zero or more questions


## ResponseHeader

text displayed before results


## responses
List&lt;[ResponseProxy](ResponseProxy)&gt;

Zero or more responses


## values
Dictionary&lt;string, string&gt;

The values for reporting, valid if Complete is true.

# Example Json

```json
{
  "questions": [
    {
      "Reference": "string",
      "Text": "string",
      "path": "string",
      "format": "string",
      "qtype": 0,
      "minval": 0,
      "maxval": 0,
      "increment": 0,
      "categories": [
        "string"
      ],
      "SResponse": "string",
      "DResponse": 0
    }
  ],
  "responses": [
    {
      "rtype": 0,
      "Preamble": "string",
      "MainText": "string",
      "Annotation": "string",
      "Value": 0,
      "LowText": "string",
      "HighText": "string",
      "Color": "string",
      "MinVal": 0,
      "MaxVal": 0,
      "format": "string"
    }
  ],
  "PercentComplete": 0,
  "Complete": true,
  "ieToken": "string",
  "ResponseHeader": "string",
  "QuestionHeader": "string",
  "Preamble": "string",
  "CanUnwind": true,
  "Language": "string",
  "values": {}
}
```