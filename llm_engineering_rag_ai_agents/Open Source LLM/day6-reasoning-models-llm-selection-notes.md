# Reasoning LLMs in Hugging Face & Leaderboards

## Notebook Walkthrough (Easy Language)

This guide explains what each major section of the notebook is doing.

------------------------------------------------------------------------

## Step 1: - \*\*Important: This Notebook requires GPU access on Google Colab. You can access

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 2: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABeIAAANPCAYAAAC2La84A

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 3: TASK 1. PROJECT OVERVIEW & KEY LEARNING OBJECTIVES

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 4: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABeMAAANLCAYAAADCfoYQA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 5: In our previous project, we explored running open-source models for document Q&A

**What it does**

We'll use a model from the **DeepSeek** family, known for their strength
in coding and instruction following, which often translates to better
step-by-step reasoning. We won't just classify news as positive,
negative, or neutral; we'll ask the model to explain its reasoning and
provide a tag for the news. **What We'll Build:** A system that: 1.
Loads financial news headlines

------------------------------------------------------------------------

## Step 6: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABeYAAANMCAYAAAA5Un3sA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 7: TASK 2. EXPLORE HUGGING FACE DATASETS LIBRARY & INSTALL KEY LIBRARIES

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 8: As usual, we begin by installing the necessary libraries. This time, we're addin

**What it does**

**Installing Libraries:** \* `transformers`, `accelerate`,
`bitsandbytes`, `torch`: For loading and running our DeepSeek model
efficiently. \* `datasets`: To load the financial news dataset. \*
`gradio`: For building the UI.

------------------------------------------------------------------------

## Step 9: - **Link to Datasets Library on Hugging Face: https://huggingface.co/datasets**

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 10: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Explore the datasets section on Hugging Face, How many datasets
    are present?** - **Search for News-related data, which one is the
    most downloaded?** - **Search for `all_news_finance_sm_1h2023`
    dataset. How many samples exist?** - **Visit the Data Studio and
    using AI Query Feature, select only news released by CNBC.**

------------------------------------------------------------------------

## Step 11: TASK 3. LOAD FINANCIAL NEWS DATASETS FROM HUGGING FACE

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 12: We'll use the Hugging Face `datasets` library to load the \`PaulAdversarial/all_n

**What it does**

**Steps:** 1. Use `load_dataset("dataset_name")` to download and cache
the dataset. 2. Inspect the dataset structure and features (columns). 3.
Select the relevant columns ('title' and 'description') for our
analysis. 4. Combine the title and description into a single text input
for the LLM.

------------------------------------------------------------------------

## Step 13: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Examine the "Dataset Features" output. Besides 'title' and
    'description', what other potentially interesting columns are
    available (e.g., `main_domain`, `created_at`)?** - **Modify the
    `display(...)` line in the code block to show 10 samples. Rerun the
    cell. Do the titles and descriptions seem relevant to financial
    news?** - \*\*How would you access only the `full_text` of the 100th
    news item in

------------------------------------------------------------------------

## Step 14: TASK 4. LOAD & TEST DEEPSEEK REASONING MODEL

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 15: Now, let's load our chosen "reasoning" model. We're using \`deepseek-ai/DeepSeek-

**What it does**

**Why DeepSeek for this Task?** \* **Instruction Following:** Good at
adhering to complex prompts, like our request for both reasoning and
classification in a specific format. \* **Logical Steps:** Its training
helps in breaking down the analysis into steps (the reasoning trace). \*
**Colab Friendly:** The 1.5B parameter size is manageable within the
free tier GPU memory limits when using

------------------------------------------------------------------------

## Step 16: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/kAAAR5CAYAAAAmi7bYA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 17: Let's explore the model: https://huggingface.co/deepseek-ai/deepseek-coder-1.3b-

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 18: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Try a very simple logic or math problem:**
    `python test_question = "What is the count of apples i have now, if i initially had 5 apples with me and then gave 2 to my Mom and 2 to my brother. Keep the thining short."` -
    \*\*Based on this simple test and the model's description, how might
    generating a

------------------------------------------------------------------------

## Step 19: TASK 5. A FRAMEWORK FOR CHOOSING THE RIGHT MODEL FOR YOUR BUSINESS

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 20: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAACAAAAAR0CAYAAADltPaTA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 21: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/kAAAR0CAYAAACaFaUGA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 22: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/kAAAR1CAYAAABRSXajA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 23: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/oAAAR5CAYAAADNvA3bA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 24: Google Tensorflow Playground: https://playground.tensorflow.org/

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 25: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/sAAAR6CAYAAACk6hRLA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 26: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/kAAAR6CAYAAACgH8R2A

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 27: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/oAAAR8CAYAAACdcZxoA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 28: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/oAAAR3CAYAAAD3tmyrA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 29: TASK 6. MODEL LEADERBOARDS & OLD/NEW BENCHMARKS

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 30: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/sAAAR5CAYAAAAifmblA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 31: - Old Leaderboard: https://huggingface.co/spaces/open-llm-leaderboard-old/open_l

**What it does**

-   New Leaderboard:
    https://huggingface.co/spaces/open-llm-leaderboard/open_llm_leaderboard#/ -
    Performance Leaderboard:
    https://huggingface.co/spaces/optimum/llm-perf-leaderboard - Big
    Code Models Leaderboard:
    https://huggingface.co/spaces/bigcode/bigcode-models-leaderboard -
    Medical Leaderboard:
    https://huggingface.co/spaces/openlifescienceai/open_medical_llm_leaderboard

------------------------------------------------------------------------

## Step 32: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/oAAAR1CAYAAAC6fs2gA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 33: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/gAAAR2CAYAAAA4H28zA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 34: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/UAAAR3CAYAAAAGvTcmA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 35: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/gAAAR0CAYAAAB11844A

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 36: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/oAAAR7CAYAAACAdKzQA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 37: TASK 7. PROMPTING FOR REASONING & CLASSIFICATION

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 38: This is the core of our project! We need to craft a prompt that tells the DeepSe

**What it does**

1.  **Analyze** the provided financial news text (`full_text`). 2.
    **Think step-by-step** from a financial perspective: why might this
    news be positive, negative, or neutral for the mentioned entities or
    the market? 3. **Output the reasoning** clearly labeled. 4. **Output
    the final classification** (one of: Positive, Negative, Neutral)
    clearly labeled. Using clear labels or delimiters in the prompt
    helps the model

------------------------------------------------------------------------

## Step 39: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Find an interesting news item by looking at the sample data (or
    pick a specific index, e.g., `index = 0`). Modify the test loop at
    the end of the code block above to analyze only that specific index
    instead of random ones. Run the cell. Do the reasoning and
    classification seem appropriate for that news item?**

------------------------------------------------------------------------

## Step 40: TASK 8. BUILDING THE GRADIO INTERFACE

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 41: Let's wrap our analysis function in a user-friendly Gradio interface. Users shou

**What it does**

**Interface Elements:** \* A Textbox to display the news item
(`full_text`). \* A button to fetch a new random news item. \* A button
to trigger the analysis. \* Two Textboxes (or Markdown elements) to
display the Reasoning and the Classification separately.

------------------------------------------------------------------------

## Step 42: PRACTICE OPPORTUNITY SOLUTIONS

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 43: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Explore the datasets section on Hugging Face, How many datasets
    are present?** - **Search for News-related data, which one is the
    most downloaded?** - **Search for `all_news_finance_sm_1h2023`
    dataset. How many samples exist?** - **Visit the Data Studio and
    using AI Query Feature, select only news released by CNBC.**

------------------------------------------------------------------------

## Step 44: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB10AAAQFCAYAAAD62NHJA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 45: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Examine the "Dataset Features" output. Besides 'title' and
    'description', what other potentially interesting columns are
    available (e.g., `main_domain`, `created_at`)?** - **Modify the
    `display(...)` line in the code block to show 10 samples. Rerun the
    cell. Do the titles and descriptions seem relevant to financial
    news?** - \*\*How would you access only the `full_text` of the 100th
    news item in

------------------------------------------------------------------------

## Step 46: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Try a very simple logic or math problem:**
    `python test_question = "What is the count of apples i have now, if i initially had 5 apples with me and then gave 2 to my Mom and 2 to my brother. Keep the thining short."` -
    \*\*Based on this simple test and the model's description, how might
    generating a

------------------------------------------------------------------------

## Step 47: - A general chat model might answer the sentiment question conversationally ("I

**What it does**

-   DeepSeek's strengths useful here are: - **Instruction Adherence:**
    Following the multi-part instructions in the prompt. - **Structured
    Output:** Generating text in a predictable format with delimiters. -
    **(Implied) Logical Flow:** Applying analytical steps (even if
    simple) to connect the news content to the sentiment, which forms
    the basis of the reasoning trace.

------------------------------------------------------------------------

## Step 48: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Find an interesting news item by looking at the sample data (or
    pick a specific index, e.g., `index = 0`). Modify the test loop at
    the end of the code block above to analyze only that specific index
    instead of random ones. Run the cell. Do the reasoning and
    classification seem appropriate for that news item?**

------------------------------------------------------------------------

## Step 49: - Would love to connect with you on LinkedIn: https://www.linkedin.com/in/dr-rya

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 50: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAB/kAAAR1CAYAAABRSXajA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Step 51: \![image.png\](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABd8AAANOCAYAAADgfHUVA

**What it does**

This section introduces the next part of the notebook.

------------------------------------------------------------------------

## Overall Idea

Read the notebook from top to bottom. Each section builds on the
previous one, so execute the cells in order and verify the output before
moving ahead.
