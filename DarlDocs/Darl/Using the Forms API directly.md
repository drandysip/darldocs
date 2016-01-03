Using the Forms API directly
===

You can call the underlying DARL API directly for functionality outside of Logic Apps or Azure.

You can see all the available the calls [here](https://darlinf.portal.azure-api.net/docs/services/558ac66cfdc98312f078a65b/operations/558ac66dfdc9830d303b11d3). 

# The general process

For a forms display of some kind there are three calls you need described here:

[QSet_Get](https://darlinf.portal.azure-api.net/docs/services/558ac66cfdc98312f078a65b/operations/558ac66dfdc9830d303b11d2) which opens the initial form conversation,
[QSet_Post](https://darlinf.portal.azure-api.net/docs/services/558ac66cfdc98312f078a65b/operations/558ac66dfdc9830d303b11d5) which exchanges data with the conversation and
[QSet_Delete](https://darlinf.portal.azure-api.net/docs/services/558ac66cfdc98312f078a65b/operations/558ac66dfdc9830d303b11d4) which acts as a "back" button.

The QSet_Get call is used initially. You call it with your subscription key and the id of the project you are using.
It returns a [QuestionSetProxy](../DarlCommon/QuestionSetProxy) class.
This contains an id in [ieToken](../DarlCommon/QuestionSetProxy#ieToken) which represents the current conversation. Use this, rather than the project key in all further transactions.

The [QuestionSetProxy](../DarlCommon/QuestionSetProxy) also contains the first questions.
The number of these is the number of unanswered, necessary questions or the [form editor](form editor) default question count, whichever is smaller.
The questions are formatted as  [QuestionProxy](../DarlCommon/QuestionProxy) classes.

You should display these questions and insert the responses back into your copy of the initial QuestionSetProxy.
You then continue the process by calling QSet_Post with the updated QuestionSetProxy, which returns a new version of the same.
This process continues until the [QuestionSetProxy.Complete flag](../DarlCommon/QuestionSetProxy#Complete) becomes true. 
At that point the list of questions will be empty and some responses will be available in the responses list.
You should display these to the user.
At any time if the [QuestionSetProxy.CanUnwind](../DarlCommon/QuestionSetProxy#CanUnwind) flag is true you can call QSet_Delete function to delete the last set of answers. This will return a new QuestionSetProxy reflecting the previous state of the system.

# Displaying questions

How you display the questions is very much up to you. Different media will have different requirements. [DarlConverse](Darl Converse) For instance is an API app that will communicate with emails and social media.
For emails formatting must be entirely textual. For a web or App based interface you can use controls.
Questions can be of three types, and each can be displayed differently.

+ numeric, displayable as edit controls with range validation, spinners or sliders

+ categorical, displayable as a drop down control filled from the categories property.

+ textual, as an edit or text control with optional regular expression validation.


# Inserting the responses
Each [QuestionProxy](../DarlCommon/QuestionProxy) has an SResponse and a DResponse property.
For numeric inputs put a double value into DResponse, for categorical or textual put a text response into SResponse. 
For categorical questions the response should match exactly one of the categories.

# Displaying responses

Again this is down to you how these are displayed. We support a variety of representations.
Numeric values can be displayed textually or as a Score Bar. For the latter we supply the numeric range of the score bar, the actual value to display and text to put to the left and right of the bar.
Textual values are either just text or a link to take the user off to some other page.

# Reporting
In many usage scenarios you will want to do something else with the data collected other than display it to the user.
You can individually decide which outputs of the rule set to display to the user as responses.
The entire data set, including questions and all the inferred output values will be available QuestionSetProxy.values property as a set of name value pairs.
It is therefore straightforward to trigger some other process and pass this data set on.

# Reference examples

+ DarlConverse illustrates a purely textual approach to using the system. The full code can be viewed [here](https://github.com/drandysip/DarlConverse).

+ DarlForms uses HTML controls to display a form. View the code [here](https://github.com/drandysip/DarlForms).

# Caching and restarting
All form sessions are cached for 24 hours. If you want to handle dropping and restarting of a questionnaire you can do this by storing  the [ieToken](../DarlCommon/QuestionSetProxy#ieToken) and then generate a restart by calling QSet_Get with the ieToken instead of the project ID.
The QuestionSetProxy returned will represent the last state as seen by the system.

# The DarlCommon Library
If you are developing using .Net the set of classes used by the API is available in the DarlCommon DLL. 
This is available via NuGet with the name DarlCommon. More details [here](https://www.nuget.org/packages/DarlCommon/).
The reference examples demonstrate using this package.



