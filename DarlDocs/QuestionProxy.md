Class QuestionProxy
===

Represents a single question displayed on a form

# Properties


## categories
List&lt;string&gt;

A list of permissible categories if categorical. 
Use as choices in a drop down.


## DResponse
double

A numeric response from the user.


## format

A regular expression that can be used to validate a textual input.


## increment

The increment to use for number selection - 1 for integers, 0 for continuum etc.


## maxval

If numeric the upper bound (+infinity if unbounded)


## minval

If numeric the lower bound (-infinity if unbounded)


## path
string

Gets or sets the path. (reserved for future use)


## qtype
QType

The type of the question



## Reference

The id of the question


## SResponse

textual response from the user.


## Text

The text of the question

# Enumerations

## QType

Used to define the data type

| values | use | integer value |
|----|----|----|
|categorical|categorical input|1|
|numeric|Numerical input|0|
|textual|Textual input|2|


