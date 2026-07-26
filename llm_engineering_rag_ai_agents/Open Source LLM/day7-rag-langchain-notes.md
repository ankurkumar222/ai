# RAG & LangChain Lab -- Ask Eleven Madison Park Restaurant

## Notebook Walkthrough (Easy Language)

This guide explains what each major part of the notebook is doing in
simple language.

## Big Picture

``` text
Restaurant Documents
        ↓
Load Documents
        ↓
Split into Chunks
        ↓
Create Embeddings
        ↓
Store in Vector Database
        ↓
User asks a Question
        ↓
Retrieve Relevant Chunks
        ↓
Send Context + Question to LLM
        ↓
Generate Answer
```

------------------------------------------------------------------------

## Step 1: TASK 1: PROJECT OVERVIEW & KEY LEARNING OBJECTIVES

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 2: ![image.png](attachment:01e041fe-619d-44e6-8903-d6f03244e983.png)

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 3: ![image.png](attachment:b5417376-7793-437b-973e-a43a66a68c2b.png)

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 4: ![image.png](attachment:ed082c6d-f693-4c3d-9a06-ca02fadbed8f.png)

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 5: TASK 2: UNDERSTAND RETRIEVAL AUGMENTED GENERATION (RAG)

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 6: ![image.png](attachment:0c99d96c-6dc2-4b7b-8086-4328ca32790e.png)

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 7: ![image.png](attachment:f8f3f9eb-890c-4993-9a8b-0d5dbf076b07.png)

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 8: ![image.png](attachment:8ce7c48b-6bb9-4aaf-9dfb-9639ee653c2c.png)

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 9: ![image.png](attachment:e2de25cc-5cbf-453b-b43b-4725ce43f6b5.png)

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 10: TASK 3: LANGCHAIN 101

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 11: ![image.png](attachment:15015fd4-74e5-448c-93eb-223ecc2549d2.png)

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 12: ![image.png](attachment:5416184c-f374-4632-8447-519a47b5094e.png)

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 13: TASK 4. SETUP, GATHER RAG TOOLS, & LOAD THE DATA

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 14: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Display the last 750 characters in the loaded document** -
    **Perform a sanity check by comparing the printed characters to
    `eleven_madison_park_data.txt` file** - **Print the email and the
    phone number of the restaurant**

------------------------------------------------------------------------

## Step 15: TASK 5. SPLITTING DOCUMENTS (CHUNKING) WITH LANGCHAIN TEXT SPLITTER

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 16: Large documents are hard for AI models to process efficiently and make it difficult to find specific answers. We need to split the loaded document into smaller, manageable "chunks". We'll use Langchain's `RecursiveCharacterTextSplitter`.

**What it does**

-   **Why chunk?** Smaller pieces are easier to embed, store, and
    retrieve accurately. \* **`chunk_size`**: Max characters per chunk.
    \* **`chunk_overlap`**: Characters shared between consecutive chunks
    (helps maintain context).

------------------------------------------------------------------------

## Step 17: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Change `chunk_size` to `500` in the
    `RecursiveCharacterTextSplitter` and re-run the cell. How many
    chunks do you get now? Is it more or less than before? Change it
    back to `1000`** - **Change `chunk_overlap` to `0` and re-run the
    cell. Does the number of chunks change drastically? What problem
    might setting overlap to 0 cause? Change it back to `150`** -
    \*\*Print the last example chunk and its metadata and

------------------------------------------------------------------------

## Step 18: TASK 6. EMBEDDINGS AND VECTOR STORE CREATION

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 19: ![image.png](attachment:84a7928c-59d4-4390-b7ca-3692a003465a.png)

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 20: ![image.png](attachment:59f18738-3814-4b55-a9f5-8c954d21660a.png)

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 21: ![image.png](attachment:abed78b5-eaba-4db8-be1f-f47021df3f68.png)

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 22: Now, we convert our text chunks into **embeddings** (numerical vectors) using OpenAI. Similar text chunks will have similar vectors. We then store these vectors in a **vector store** (ChromaDB) for fast searching.

**What it does**

-   **Embeddings:** Text -\> Numbers (Vectors) representing meaning. \*
    **Vector Store:** Database optimized for searching these vectors.

------------------------------------------------------------------------

## Step 23: Tensorflow Ebeddings projector (it's fun!): https://projector.tensorflow.org/

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 24: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Using Tensorflow Embeddings Projector, explore the nearest points
    to "Italy"** - **Choose 2 additional different words that you
    like** - **Tensorflow Ebeddings projector:
    https://projector.tensorflow.org/**

------------------------------------------------------------------------

## Step 25: TASK 7. TESTING THE RETRIEVAL

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 26: Before building the full Q&A chain, let's test if our vector store can find relevant chunks based on a sample question. We'll use the `similarity_search` method.

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 27: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Change the `test_query` variable to ask one of the following
    questions. Re-run the cell for each question. Do the retrieved
    document snippets seem relevant to your question?** -
    `"Who is Daniel Humm?"` - `"Is there a dress code?"` -
    `"Tell me about the partnership with Magic Farms."` -
    `"How do I make a reservation?"` - \*\*Adjust the value of k to
    `k=1` and then to `k=5`. Re-run the cell.

------------------------------------------------------------------------

## Step 28: TASK 8. BUILDING & TESTING THE RAG CHAIN USING LANGCHAIN

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 29: Now we assemble the core RAG logic using Langchain's `RetrievalQAWithSourcesChain`. This chain combines:

**What it does**

1.  A **Retriever**: Fetches relevant documents from our
    `vector_store`. 2. An **LLM**: Generates the answer based on the
    question and retrieved documents (we'll use OpenAI). This specific
    chain type automatically handles retrieving documents, formatting
    them with the question for the LLM, and tracking the sources.

------------------------------------------------------------------------

## Step 30: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Look at the `result` dictionary printed by the chain test. What
    are the key pieces of information it contains?** - **Change
    `temperature=0` to `temperature=1.3` in the `llm = OpenAI(...)`
    line. Re-run the cell and ask the *same* `chain_test_query`. Does
    the wording of the answer change slightly? Change it back to
    `0`.** - \*\*Set `verbose=True` and `return_source_documents=True`
    in the `RetrievalQAWithSourcesChain.from_chain_type(...)` line.
    Re-run the cell. What extra information do you see

------------------------------------------------------------------------

## Step 31: TASK 9. CREATING A GRADIO INTERFACE FOR OUR RAG CHAIN

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 32: Let's wrap our RAG chain in a user-friendly web interface using Gradio. Users will type a question, click a button, and see the answer along with the sources the AI used.

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 33: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Expand on the example questions to include the ones below. Rerun
    the app and test them out.** - **"Do I need a reservation for the
    bar?"** - **"What is the dress code?** - **"Can I buy gift
    cards?"** - **Change the text on the submit button from
    `Ask Question` to `Ask Eleven Madison Park AI 🤖`. Where do you make
    this change?** - \*\*We already added a `gr.ClearButton` in

------------------------------------------------------------------------

## Step 34: PRACTICE OPPORTUNITY SOLUTIONS

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 35: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Display the last 750 characters in the loaded document** -
    **Perform a sanity check by comparing the printed characters to
    `eleven_madison_park_data.txt` file** - **Print the email and the
    phone number of the restaurant**

------------------------------------------------------------------------

## Step 36: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Change `chunk_size` to `500` in the
    `RecursiveCharacterTextSplitter` and re-run the cell. How many
    chunks do you get now? Is it more or less than before? Change it
    back to `1000`** - **Change `chunk_overlap` to `0` and re-run the
    cell. Does the number of chunks change drastically? What problem
    might setting overlap to 0 cause? Change it back to `150`** -
    \*\*Print the last example chunk and its metadata and

------------------------------------------------------------------------

## Step 37: 1. Changing `chunk_size=500` will result in *more* chunks being created because the original document is being divided into smaller pieces. The exact number depends on the total text length and overlap.

**What it does**

2.  Changing `chunk_overlap=0` might slightly change the total number of
    chunks, but usually not by a large amount compared to changing the
    chunk size. The potential problem with zero overlap is that if an
    important sentence or idea happens to fall exactly on the boundary
    between two chunks, it might get cut in half, and the full context
    could be lost in both resulting chunks. Overlap mitigates this by
    ensuring

------------------------------------------------------------------------

## Step 38: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Using Tensorflow Embeddings Projector, explore the nearest points
    to "Italy"** - **Choose 2 additional different words that you
    like** - **Tensorflow Ebeddings projector:
    https://projector.tensorflow.org/**

------------------------------------------------------------------------

## Step 39: ![image.png](attachment:e8df0fdd-95e7-4f23-9b6a-f9c93d3cbed5.png)

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 40: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Change the `test_query` variable to ask one of the following
    questions. Re-run the cell for each question. Do the retrieved
    document snippets seem relevant to your question?** -
    `"Who is Daniel Humm?"` - `"Is there a dress code?"` -
    `"Tell me about the partnership with Magic Farms."` -
    `"How do I make a reservation?"` - \*\*Adjust the value of k to
    `k=1` and then to `k=5`. Re-run the cell.

------------------------------------------------------------------------

## Step 41: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Look at the `result` dictionary printed by the chain test. What
    are the key pieces of information it contains?** - **Change
    `temperature=0` to `temperature=1.3` in the `llm = OpenAI(...)`
    line. Re-run the cell and ask the *same* `chain_test_query`. Does
    the wording of the answer change slightly? Change it back to
    `0`.** - \*\*Set `verbose=True` and `return_source_documents=True`
    in the `RetrievalQAWithSourcesChain.from_chain_type(...)` line.
    Re-run the cell. What extra information do you see

------------------------------------------------------------------------

## Step 42: 1. **Chain Output:** The `result` dictionary from `RetrievalQAWithSourcesChain` typically contains:

**What it does**

-   `'question'`: The original input question. \* `'answer'`: The
    textual answer generated by the LLM based on the retrieved context.
    \* `'sources'`: A string listing the source(s) identified (often the
    filename from the metadata of the used documents). \*
    `'source_documents'`: If `return_source_documents=True`, this key
    holds a list of the actual Langchain `Document` objects that were
    retrieved and passed to the LLM. 2. **Temperature Effect:** Changing
    `temperature=1.3` introduces more randomness into

------------------------------------------------------------------------

## Step 43: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Expand on the example questions to include the ones below. Rerun
    the app and test them out.** - **"Do I need a reservation for the
    bar?"** - **"What is the dress code?** - **"Can I buy gift
    cards?"** - **Change the text on the submit button from
    `Ask Question` to `Ask Eleven Madison Park AI 🤖`. Where do you make
    this change?** - \*\*We already added a `gr.ClearButton` in

------------------------------------------------------------------------

## Step 44: ![image.png](attachment:8487929a-c0b8-4f1c-88be-c422bcca486b.png)

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

## Step 45: ![image.png](attachment:599c4221-1f20-4ddc-b18e-fcc855aa2fc9.png)

**What it does**

This section introduces the next step in the notebook.

------------------------------------------------------------------------

# Overall Workflow

``` text
Install Libraries
      ↓
Load Restaurant Documents
      ↓
Split into Small Chunks
      ↓
Generate Embeddings
      ↓
Store in Vector Database
      ↓
User asks a Question
      ↓
Retriever finds relevant chunks
      ↓
LLM receives:
Question + Retrieved Context
      ↓
LLM generates final answer
```

## One-Line Summary

This notebook demonstrates how to build a **Retrieval-Augmented
Generation (RAG)** application using **LangChain**. Instead of relying
only on the LLM's memory, it retrieves relevant restaurant information
from documents and provides grounded answers.
