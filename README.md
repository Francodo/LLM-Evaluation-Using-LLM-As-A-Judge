This experiment evaluate the accuracy or correctness of an LLM response to a given prompt. A labelled dataset(Questions and Answers), converted into a table column (table of information) is given to the 
source LLM in the application. Gemini model or Claude model will be used to judge the response of source LLM for correctness. This allows us to test and understand how good the model is working.

BinaryClassificationPromptTemplate is used as LLM Evaluation method. Classify as CORRECT or INCORRECT

Output or Report is generated with metrics - ColumnDistributionMetric for analytics (a count graph) as distribution.

EvidentlyAI SDK is used for this application.

I defined the target_response, new_response as reference data

The output can be extracted as json and stored as dict() for input into another application.

Output consists of Question, Target_Response, New Response, Label, Comment, Correctness, Correctness Reasoning.
Note that Correctness_Reasoning provides the reasoning behind judgement decision.

It requires an API Key from Google or Anthropic if using Claude
