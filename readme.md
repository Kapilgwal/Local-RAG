# Creating a Local RAG pipeline from Scratch

Creating a Local RAG(Retrival Augmented Generation).
The goal of RAG is to take information and pass it an LLM so it can generate ouptut based on the information

* Retrieval : It is like a search the relevant information given a query from a textbook of your choice

* Augmented : We want to take the relevant info and augment the input prompt to an llm with the relevant info

* Generation : Take first two steps and pass the llm to generate the output

# WHY RAG?

The main goal of RAG is to improve the genration output of the LLM.

1. Prevent Halluncination - llm are incredibly good at generation good looking text however the text looks good but it may not need to be correct. we want question to be answered with specific context and the factually accurate.

2. Custom data : Many base llm are trained with internet scale data this means they have a fairly good understanding of language in general.However it also doesa lotof their responses can be generic in nature so rag helps to create specific responses based on specific documents

# What can RAG used for?

* Customer support Q&A chat - Treat your existing customer support documents as a resource and when a customer asks a question  you could have retrieval system documentation snippets and then have an llm craft those snipeets into an answer think of this as a chatbot for documentations

There are multiple use cases like email chain analysis,Company internal docmentation chat,Textbook Q&A

# Why would we care about token count ?
Token count is important to think about :
1. Embedding models don't dealt with infinite tokens
2. LLMs don't deal with infinite tokens

# Chunking
The concept of splitting larger pieces of text into smaller ones is often referred as text splitting or chinking.There is no 100% correct way

There are frameworks which can do things like langchain but we will like to try by ourself then langchain

# Why do we do chinking
1. So our text are easier to filter
2. So our text chunks can fit into our embedding model context window
3. So our contexts passed to an LLM can be more specified and focused

# Splitting each chinks into its own item

We'd like to embed each chunk of sentences into its own numerical representation 

That'll give us a good level of granularity

We can dive specifically into the text_sample that was used in our model