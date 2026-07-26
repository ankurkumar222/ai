# Chat with Documents Using Hugging Face Open-Source LLMs

## Notebook Walkthrough (Easy Language)

This guide explains what each major section of the notebook is doing.

------------------------------------------------------------------------

## Step 1: - \*\*Important: This Notebook requires GPU access on Google Colab. You can access

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 2: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/YAAAR5CAYAAADXgO1VA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 3: TASK 1. UNDERSTAND THE PROBELM STATMENT & KEY LEARNING OBJECTIVES

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 4: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/0AAAR1CAYAAABYotbZA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 5: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABeEAAANLCAYAAADGi1YtA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 6: TASK 2. EXPLORE HUGGING FACE!

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 7: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/oAAAR4CAYAAAAG4N5+A

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 8: - Hugging Face: https://huggingface.co/models

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 9: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/oAAAR5CAYAAADNvA3bA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 10: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Visit [huggingface.co/models](https://huggingface.co/models) and
    filter for Text Generation on the left sidebar, find the "Tasks"
    filter and select "Text Generation".** - **Sort by Downloads: Near
    the top right, you can sort the models. Try sorting by "Most
    Downloads". What are some of the most popular text generation models
    you see?** - \*\*Search for models with "phi", "gemma", "qwen", or
    "llama"

------------------------------------------------------------------------

## Step 11: TASK 3. INSTALL KEY LIBRARIES, OBTAIN HF ACCESS TOKENS, & GPU CHECK

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 12: We need to install the necessary Python libraries. We'll also need to potentiall

**What it does**

**Installing Libraries:** \* `transformers`: The core Hugging Face
library for models and tokenizers. \* `accelerate`: Helps run models
efficiently across different hardware (like GPUs) and use less memory.
\* `bitsandbytes`: Enables model quantization (like loading in 4-bit or
8-bit), drastically reducing memory usage. Essential for running decent
models on free Colab GPUs! \* `torch`: The underlying deep learning
framework (PyTorch).

------------------------------------------------------------------------

## Step 13: **Hugging Face Hub Login:**

**What it does**

Some models on the Hugging Face Hub are "gated," meaning you need to
agree to their terms and conditions before downloading. Logging in
allows the `transformers` library to download these models if needed. \*
**Get a Hugging Face Token:** 1. Go to
[huggingface.co](https://huggingface.co/). 2. Sign up or log in. 3.
Click your profile picture (top right) -\> Settings -\> Access

------------------------------------------------------------------------

## Step 14: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Go to "Runtime" -\> "Change runtime type" and explore available
    hardware accelerator types in your Colab.** - **Compare CPUs, T4
    GPU, A100 GPU from a performance standpoint. What speed gains can
    developers get by shifting from a CPU to A100 GPU?**

------------------------------------------------------------------------

## Step 15: TASK 4. HUGGING FACE TRANSFORMERS LIBRARY: PIPELINES

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 16: - **`transformers`:** A Python library that provides a standardized way to downl

**What it does**

-   `pipeline()`: A high-level, easy-to-use abstraction for common tasks
    (like text generation, summarization). Great for quick tests and
    beginners. \* `AutoTokenizer`: Automatically downloads the correct
    "tokenizer" for a model. A tokenizer converts human-readable text
    into numerical IDs the model understands. \* `AutoModelFor...`:
    Automatically downloads the correct model architecture and
    pre-trained weights (e.g., `AutoModelForCausalLM` for text
    generation models like GPT, Llama,

------------------------------------------------------------------------

## Step 17: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/kAAAR6CAYAAACgH8R2A

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 18: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/sAAAR4CAYAAADpIrVAA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 19: - Attention Is All You Need: https://arxiv.org/abs/1706.03762

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 20: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Use Hugging Face's pipeline() function and the ProsusAI/finbert
    model to analyze sentiment in financial news using the following
    examples:** - **news_samples = \["Tesla stock surged after
    record-breaking quarterly earnings.", "Microsoft is scheduled to
    release its earnings report next week."\]** - **Compare the results
    with Hugging Face's finbert Inference API and perform a sanity
    check**

------------------------------------------------------------------------

## Step 21: TASK 5. HUGGING FACE TRANSFORMERS LIBRARY: AUTOTOKENIZERS

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 22: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABycAAAORCAYAAABY465DA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 23: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Use the AutoTokenizer.from_pretrained() method to load a different
    tokenizer (e.g., "bert-base-uncased" or "facebook/opt-125m")** -
    **Try encoding a new sentence like: "Generative AI is transforming
    the future of work.** - **Print both: The raw tokens
    (tokenizer.tokenize(text)) and the input IDs
    (tokenizer(text)\["input_ids"\])** - **Compare the tokenization
    between two models. What differences do you observe when handling
    spaces between words?**

------------------------------------------------------------------------

## Step 24: TASK 6. HUGGING FACE TRANSFORMERS LIBRARY: AutoModelForCausalLM

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 25: AutoModelForCausalLM is a Hugging Face class that automatically loads a pretrain

**What it does**

Let's get hands-on and load a model! We'll start with a relatively small
but capable model that should fit comfortably in Colab's free tier GPU
memory, thanks to quantization. **Key Steps:** 1. **Choose a Model ID:**
We need the unique identifier from the Hugging Face Hub (e.g.,
`"google/gemma-2b-it"` or `"microsoft/Phi-3-mini-4k-instruct"`). 2.
**Load the Tokenizer:** Use `AutoTokenizer.from_pretrained(model_id)` to
get the specific

------------------------------------------------------------------------

## Step 26: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Modify the `prompt` variable. Ask a different question, like
    `"What is the capital of France?"` or
    `"Write a short poem about a cat."` Run the cell again. How does the
    model respond?**

------------------------------------------------------------------------

## Step 27: TASK 7. READ PDF DOCUMENTS & EXTRACT TEXT USING PYPDF LIBRARY

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 28: Now that we have a model loaded, we need the text from our document to ask quest

**What it does**

For this example, we'll download a sample PDF about climate change. You
can easily adapt this to use your own PDF by uploading it to Colab.
**Steps:** 1. **Get the PDF:** Download it or specify the path if
uploaded. 2. **Open the PDF:** Use `pypdf.PdfReader`. 3. **Iterate
Through Pages:** Loop through each page in the PDF. 4. **Extract Text:**
Use

------------------------------------------------------------------------

## Step 29: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Print the last 500 characters of the PDF Document.** - **Compare
    the results to the PDF content and perform a sanity check.**

------------------------------------------------------------------------

## Step 30: TASK 8. BUILD THE Q&A LOGIC & PROMPT THE MODEL

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 31: Now we have the two key ingredients:

**What it does**

1.  A loaded open-source LLM (and its tokenizer/pipeline). 2. The text
    content extracted from our PDF document. We need to combine these to
    answer user questions. The core idea is **prompt engineering**:
    We'll create a prompt that includes both the user's question and the
    relevant document context, instructing the model to answer based
    only on that context. **Steps:** 1. \*\*Define

------------------------------------------------------------------------

## Step 32: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Try asking a different question about the earnings call transcript
    and test the model. Try "How many monthly users are using AI?"**

------------------------------------------------------------------------

## Step 33: TASK 9. SWITCH MODELS & BUILD GRADIO INTERFACE

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 34: We have a working Q&A system with one model. But the beauty of Hugging Face is t

**What it does**

**Challenges & Approach:** \* **Loading Multiple Models:** Loading
several LLMs simultaneously (even quantized) will likely exceed Colab's
free GPU memory. \* **Solution:** We'll load one model at a time based
on the user's selection in the Gradio interface. This means unloading
the previous model before loading the new one. This will introduce a
loading delay when switching models, but it's

------------------------------------------------------------------------

## Step 35: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Visit Hugging Face Hub and choose a different model such as "Qwen
    2.5". Choose a resonable model size.** - **Modify the code above to
    add a new model to the list of available Models.** - **Test the
    newly added model and comment on the its performance**

------------------------------------------------------------------------

## Step 36: PRACTICE OPPORTUNITIES SOLUTIONS

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 37: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Visit [huggingface.co/models](https://huggingface.co/models) and
    filter for Text Generation on the left sidebar, find the "Tasks"
    filter and select "Text Generation". Near the top right, you can
    sort the models. Try sorting by "Most Downloads". What are some of
    the most popular text generation models you see?** - \*\*Search for
    models with "phi", "gemma", "qwen", or "llama" in their names, often

------------------------------------------------------------------------

## Step 38: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAACiMAAATqCAYAAAA+3oCyA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 39: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Go to "Runtime" -\> "Change runtime type" and explore available
    hardware accelerator types in your Colab.** - **Compare CPUs, T4
    GPU, A100 GPU from a performance standpoint. What speed gains can
    developers get by shifting from a CPU to A100 GPU?**

------------------------------------------------------------------------

## Step 40: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABYYAAAGnCAYAAAADqYP0A

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 41: A100 GPUs: https://www.nvidia.com/en-us/data-center/a100/

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 42: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Use Hugging Face's pipeline() function and the ProsusAI/finbert
    model to analyze sentiment in financial news using the following
    examples:** - **news_samples = \["Tesla stock surged after
    record-breaking quarterly earnings.", "Microsoft is scheduled to
    release its earnings report next week."\]** - **Compare the results
    with Hugging Face's finbert Inference API and perform a sanity
    check**

------------------------------------------------------------------------

## Step 43: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAACy8AAAQzCAYAAADQXfIbA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 44: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Use the AutoTokenizer.from_pretrained() method to load a different
    tokenizer (e.g., "bert-base-uncased" or "facebook/opt-125m")** -
    **Try encoding a new sentence like: "Generative AI is transforming
    the future of work.** - **Print both: The raw tokens
    (tokenizer.tokenize(text)) and the input IDs
    (tokenizer(text)\["input_ids"\])** - **Compare the tokenization
    between two models. What differences do you observe when handling
    spaces between words?**

------------------------------------------------------------------------

## Step 45: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Modify the `prompt` variable. Ask a different question, like
    `"What is the capital of France?"` or
    `"Write a short poem about a cat."` Run the cell again. How does the
    model respond?** - **Try a different model such as
    `microsoft/Phi-4-mini-instruct` and compare the outputs from both
    models**

------------------------------------------------------------------------

## Step 46: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Print the last 500 characters of the PDF Document.** - **Compare
    the results to the PDF content and perform a sanity check.**

------------------------------------------------------------------------

## Step 47: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Try asking a different question about the earnings call transcript
    and test the model. Try "How many monthly users are using AI?"**

------------------------------------------------------------------------

## Step 48: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Visit Hugging Face Hub and choose a different model such as "Qwen
    2.5". Choose a resonable model size.** - **Modify the code above to
    add a new model to the list of available Models.** - **Test the
    newly added model and comment on the its performance**

------------------------------------------------------------------------

## Step 49: - Would love to connect with you on LinkedIn: https://www.linkedin.com/in/dr-rya

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 50: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABegAAANOCAYAAABqU+xUA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 51: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABeAAAANNCAYAAAD/EN4OA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Overall Idea

Read the notebook from top to bottom. Each section builds on the
previous one, so execute the cells in order and verify the output before
moving ahead.
