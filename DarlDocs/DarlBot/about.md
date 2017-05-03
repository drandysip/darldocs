DARLBot
========

DarlBot is a system for generating bots. It follows in a long line of such systems including AIML, but it has important differences. 

It is optimised to give the maximum “bang per buck” both in terms of features and simplicity in creation. It also integrates in with the DARL range of products and the DARL language.

With the DarlBot editor you can specify a sequence of words that lead to a given response, or more powerfully a sequence of concepts. These concepts match up with any word with the same meaning and are drawn from a thesaurus (WordNet) of the language employed. The users’ interactions can contain multiple primitive sequences that are individually recognised and “stacked” for processing.

The processing part is both the generation of a response and the performance of background work. For instance, having worked out the user is asking for the time, you need to retrieve it and return it. 

We use the DARL language to perform the background processing, reasoning and inference.

DARL has a facility for creating questionnaires from rule sets, and these can be used with Bots too. 

The difference between these two forms of bot interaction is that whereas DarlBot is guided by the user and attempts to answer any question, the questionnaire format imposes a series of choices on the user.  Clearly the two forms are appropriate in different areas. Having established with the first form that the user wants to apply for a mortgage, for instance, DarlBot can switch to a questionnaire format interaction with the user.

#The Editing interface

All statements in a computer language can be reduced to Parse Trees, trees containing the elements of an expression represented as a hierarchy. Human language, and we will concentrate here initially on English, is more complicated, but we can go a long way with parse trees too.

So, the central idea of DarlBot is that the communication model used for a bot can be encoded as a tree, and this paradigm is at the centre of the user interface.

In reality, a Directed Acyclic Graph, (DAG) is a much better model of language interactions, and this is used internally, but the DarlBot UI and runtime engine seamlessly convert between these two representations without you having to worry.
