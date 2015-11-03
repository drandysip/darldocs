Using Darl and the API apps.
============


# Introduction
DarlForms and DarlInf are two API apps that can be used on their own or with the Azure Logic app to add intelligence to back office processing.

# Darl 

Behind both apps, and several more we have coming soon, is the Darl inference engine and [language](darl). 
Darl makes it easy to create expert systems that encapsulate human knowledge. Darl can make inferences with incomplete knowledge like a human expert, and thus can be used to add vital processing capability to your workflows.

Whenever a decision making step is needed, Darl can help. 
It can do far more than just implement a piece of logic; it encapsulates a complete system for handling Fuzzy Logic, Fuzzy arithmetic, Fuzzy sets, confidence values and tolerances. 

The great beauty of the Fuzzy suite, ([Fuzzy logic](https://en.wikipedia.org/wiki/Fuzzy_logic), [Fuzzy Arithmetic](https://en.wikipedia.org/wiki/Fuzzy_mathematics) and [Possibility theory](https://en.wikipedia.org/wiki/Possibility_theory)), is that they are supersets of normal boolean logic and natural arithmetic. You don't have to understand these principles to use Darl; it defaults to boolean and natural arithmetic. It is only when you start to add uncertainty to your rule sets that the fuzzy stuff kicks in.

There is a natural tendency in science and technology to treat systems we are trying to model as if they were perfect: perfect spheres, straight lines, certain facts. Darl plays along with this tendency; you can model using idealized equations and rules, and then subsequently add tolerances and certainty figures. When you do Darl will handle these extra pieces of information as part of the framework and correctly calculate the tolerances and certainties of the results.

Uniquely, Darl will tell you when it doesn't know something. If you program a set of rules with a gap, a set of circumstances that the rule set doesn't consider, the result will be flagged as unknown if these circumstances are encountered.  We have a tool that we will add to the Azure suite soon, that detects such "lacunae" automatically, giving you the opportunity to fix them.

# Darl forms

DarlForms applies Darl to the problem of data acquisition and decision making from individuals answers to questions. Most form engines on the market are dumb, with limited ability to change the sequence of questions based on earlier responses. For them, when a form is filled in, all you have is a bunch of responses from which a human has to make a decision.

DarlForms uses the power of Darl to both optimally collect data and generate a decision simultaneously.

In most businesses or governmental applications the source for a form is a set of rules. The purpose of the form is to establish that the data entered complies with this set of rules. The rules might be statutes, the lending  rules of a business, compliance regulations etc, but they all start as a bunch of man made rules.

The idea of DarlForms is that you enter these rules in the Darl language and it then does everything itself required to create an intelligent questionnaire. 
It analyses the rules to work out which of the pieces of information detailed, corresponding to the rule set inputs, are most salient, and ranks them according to saliency. 
It then creates a questionnaire asking the most salient questions first. Questions, that are made irrelevant by previous answers are dropped from the list. 
As soon as all the required results can be inferred the process stops, the results are generated, a push trigger is passed to the hosting Logic app or your own code and the data is passed on with it. 

As well as writing the rules you have the ability to customize the text shown with each question, as well as headers and other supporting text. When the questionnaire is complete you can choose which of the results to pass back to the customer, if any. 

Because Darl goes from the rules to the questionnaire directly, any change in the rules, from a change in business circumstances to legislation change, can be immediately reflected in the Darl code, and result in an immediate change in the questionnaire. This is with no programming, no form redesign, etc. 
