Class OutputFormat
===

Defines the format of a Darl output


# Properties


## Hide
boolean

If true this output is not displayed to the user.


## Name
string

The name of the output matching that in the associated Darl file.


## OutputType
OutType

Gets or sets the type of the output.


## ScoreBarColor
string

Gets or sets the color of the score bar if used.


## ScoreBarMaxVal
double

Gets or sets the score bar maximum value if used.


## ScoreBarMinVal
double

Gets or sets the score bar minimum value if used.


## Uncertainty
boolean

Gets or sets a value indicating whether uncertainty information is displayed.

## displayType
DisplayType

Determines how the output is displayed.


## ValueFormat

Gets or sets the value format. This is a string determining how numerical values are displayed.

# Enumerations

## DisplayType

The possible display types

| values | use | integer value |
|----|----|----|
|Link| Display as a link|3|
|ScoreBar| display as a bar|2|
|Text|Display as text|1|



## OutType

The possible output types

| values | use | integer value |
|----|----|----|
|categorical| a categorical output| 1|
|numeric| a numeric output|0|
