class ResponseProxy
===
Represents an inferred response from the inference engine being displayed to the user.

# Properties

## Annotation
string

The description of the answer


## Color
string

The color of the filled section of the score bar


## format
string

The format for numeric answers.


## HighText
string

the text to the right of the score bar if used


## LowText
string

The text to the left of the score bar if used


## MainText
string

If text, the second bit of the text, the actual answer


## MaxVal
double

the value representing 100% on the score bar or the upper possibility bound


## MinVal
double

The value representing 0 on the score bar or the lower possibility bound


## Preamble
string

Preamble text. This is used if a responseProxy is not associated with an output, but contains a message.


## rtype
RType

the type of response

## Value
double

A numeric answer value if a Score Bar is used.

# Enumerations


## RType

The types of response possible


| values | use | integer value |
|----|----|----|
|Link| Display as a link|3|
|ScoreBar| display as a bar|2|
|Text|Display as text|1|
|Preamble|Display the preamble text only|0|




