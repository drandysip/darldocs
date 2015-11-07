Class InputFormat
====

The format of a Darl input

# Properties


## Categories
List&lt;string&gt;

Gets or sets the categories.


## Increment
double

Gets or sets the increment used when editing values with a spinner type control..


## InType
InputType

Gets or sets the type of the input.


## MaxLength
integer

Gets or sets the maximum length of a textual input


## Name
string

Gets or sets the name of the input.

## NumericMax
double

Gets or sets the numeric maximum expected value for use in validation and slider controls.


## NumericMin
double

Gets or sets the numeric minimum expected value for use in validation and slider controls.


## Regex
string

Gets or sets a regular expression used to validate textual inputs.


## ShowSets
boolean

Gets or sets a value indicating whether to show set names as if they were categories.

# Enumerations

# InputType

The data type of the input

| values | use | integer value |
|----|----|----|
|categorical|categorical input|1|
|numeric|Numerical input|0|
|textual|Textual input|2|
