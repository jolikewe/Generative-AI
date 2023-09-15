## Introduction

This model serves as a reference for users who seek to create a simple question-answering Large Language Model (LLM) from a PDF document, specifically system manuals. In this example, we have used the Siemens MRI Scanner manual (pdf in repository) as our reference pdf document. The user interface is implemented via Gradio. Upon submitting a question, the model will return the top 3 sections where the answer can be found, the chapter containing the relevant information as well as relevant images. The examples section in Gradio are sample questions which can be asked to the model.

Due to different formatting of system manuals, there is a need to amend the information ingestion part of the code accordingly. In addition, the LLM portion of the code is commented out. If users prefer the output text to be a short direct answer of the input question instead of the top 3 sections of where the answer to the question can be found, uncomment the LLM code and replace the default with any relevant open-source LLM model/tokenizer.


## Set-up

The dependencies required for the modules are found in requirements.txt. Replace the document directory with that which you place the MRI Scanner PDF document. The code is written in Python 3.11.4.


## Methodology

The advantage of this model is that instead of using typical LLM models which will query the whole document, RAG is able to retrieve the top n relevant sections for us to query upon. This greatly increases the accuracy of the answer. However, I commented out the code and returned the top 3 section headings instead because for manuals, there is no need for a summarized/paraphrased answer. Usually, we query on how to fix a particular component. The best reply would be one showing the detailed steps instead of a short summary. The latter would be useful if our document is for example, a literature or a news article.

In addition, returning the relevant pages as images on the user interface allows users to see the exact format and portion of the manual in which the answer to their query is located.


## Author

Jovi Lim Ke Wei
linkedin.com/jovi-lim-ke-wei/
NUS MSc. Quantitative Finance
