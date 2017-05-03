**D**octor **A**ndys **B**ot **L**anguage
==============

#Support for Association data sources
Bots need to access external data sources, the past history of the conversation, the recorded personal details and other data items.
In order to support this DARL has been extended with the DABL runtime which enables developers to connect external sources of data.

The main language change is the addition of the *store* keyword as a new kind of declaration.

You can define multiple stores in a rule set. Each of these can act as both a source and destination for data. Types are automatically inferred from context and the appropriate conversions are performed.

To use a store define it annd use it as either an input or output. The precise association accessed is selected by the reference in the square brakets after the store name, so:

```darl
ruleset store_demo
{
	store personal;
	store conversation;

	if personal[age] > 21 then conversation[adult] will be true;
}
```
#Handling absent data and support for uncertainty.
if a data item does not exist, for instance if in the example above the client has never supplied their age, then the value returned will be marked as unknown.
The Dabl runtime exposes an interface that developers can connect data sources to. The data items will be returned as DarlVars, but it is an implementation detail whether full support for uncerttainty is supplied.
For instance, a Darl-friendly store might return a fuzzy number representing likely age if the actual age was unknown.

#Testing for data existence
The following will determine if a data value is available:
```darl
	if personal[age] is present then ...
```


#Interaction with salience
In order to work out which question to supply to a user in a questionnaire context the rule sets are searched for dependencies, and a list generated of unfilled data items that affect the rule outputs that are not yet decided.
In this process store values will be marked as present.