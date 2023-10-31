# Hallucination Leaderboard

Public LLM leaderboard computed using our Hallucination Evaluation Model. We plan to update this monthly, or sooner when appropriate.

Last updated on November 1st, 2023

|Model|Accuracy|Hallucination Rate|Answer Rate|Average Summary Length (Words)|
|----|----:|----:|----:|----:|
|GPT 4|97.0 %|3.0 %|100.0 %|81.1|
|GPT 3.5|96.5 %|3.5 %|99.6 %|84.1|
|Llama 2 70B|94.9 %|5.1 %|99.9 %|84.9|
|Llama 2 7B|94.4 %|5.6 %|99.6 %|119.9|
|Llama 2 13B|94.1 %|5.9 %|99.8 %|82.1|
|Cohere-Chat|92.5 %|7.5 %|98.0 %|74.4|
|Cohere |91.5 % |8.5 % |99.8 % |59.8 |
|Anthropic Claude 2 |91.5 % |8.5 % |99.3 % |87.5 |
|Mistral 7B |90.6 % |9.4 % |98.7 % |96.1 |
|Google Palm|87.9 % |12.1 % |92.4 % |36.2|
|Google Palm-Chat|72.8 % |27.2 % |88.8 % |221.1|

## Methodology
To determine this leaderboard, we trained a model to detect hallucinations in LLM outputs, using open source datasets from the factual consistency research in summarization models. Using a model that is competitive with the best State of the Art models, we then fed 1000 short documents to each of the models above via their APIs and asked them to summarize each short document, using only facts presented in the document. Of these 1000 documents, only 821 document were summarized by every model, with some models refusing to summarize some documents based on their content. Using these 821 documents, we then computed an accuracy (no hallucinations) and a hallucination rate (100 - accuracy) for each model. The rate at which each model refuses to respond to the prompt is detailed in the 'Answer Rate' column.

## API Details
For GPT 3.5 we used the model name ```gpt-3.5-turbo``` in their API, and ```gpt-4``` for GPT4. For the 3 Llama models, we used the Anyscale hosted endpoints for each model. For the Cohere models, we used the ```/generate``` endpoint for *Cohere*, and ```/chat``` for *Cohere-Chat*. For Anthropic, we used the largest ```claude 2``` model they offer through their API. For the Miustral 7B model, we used the  [Mistral-7B-Instruct-v0.1](https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.1) model, hosted via Hugging Face's API. For Google Palm we used the ```text-bison-001``` model, and for Google Palm Chat we used ```chat-bison-001```.

**TODO**
* Link to Github model. Replicate my HF instructions on how to use model
* Links to the 2 blog posts.

