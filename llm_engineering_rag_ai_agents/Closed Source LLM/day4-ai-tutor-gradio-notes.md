# Landing Page Generator with OpenAI, Claude, and Gemini

## Notebook Walkthrough (Easy Language)

This document explains what each major section of the notebook is doing.

## Big Picture

``` text
Setup Environment
      ↓
Load Required Libraries
      ↓
Prepare Data / Inputs
      ↓
Build AI Pipeline
      ↓
Run the Model
      ↓
Evaluate Results
      ↓
Improve / Iterate
```

------------------------------------------------------------------------

## Step 1: TASK 1: PROJECT OVERVIEW - THE AI LANDING PAGE GENERATOR

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 2: ![image.png](attachment:d42c232b-228b-4bb4-aa54-f50704c616e7.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 3: ![image.png](attachment:c72d8667-2f5d-4ca4-81a6-87eeae676818.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 4: ![image.png](attachment:c1856fec-8e7f-4ca4-98ce-7164a2436fb9.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 5: TASK 2: LLM BENCHMARKS & LEADERBOARDS

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 6: ![image.png](attachment:3f67c2da-b6e2-4394-af2a-b001ef7109cc.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 7: ![image.png](attachment:9794b653-a38b-481d-b9f9-1f2dfebc16da.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 8: - **Vellum Leaderboard: https://www.vellum.ai/llm-leaderboard**

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 9: ![image.png](attachment:815c6862-8d4a-4354-a7ba-5347be5a23d1.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 10: A fun and Scary thought:

**What it does**

-   2500 tokens per second means the model can read, process, or
    generate about 2500 words or parts of words every second. A "token"
    is usually about ¾ of a word on average (for English). - 2500
    tokens/second is roughly like reading or writing about 1800 full
    words every second. - That means Llama models are very fast that
    they can generate almost an entire short essay in one second!

------------------------------------------------------------------------

## Step 11: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Using Vellum, compare Google's Gemini 2.5 Pro model with
    Deepseek-R1 (or the latest version) based on latency, context
    window, cut-off date, and accuracy.**

------------------------------------------------------------------------

## Step 12: TASK 3: PERFROM BLIND TEST EVALUATION USING CHATBOT ARENA

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 13: - **Chatbot Arena (old): https://lmarena.ai/?leaderboard**

**What it does**

-   **Chatbot Arena (New): https://beta.lmarena.ai/leaderboard**

------------------------------------------------------------------------

## Step 14: ![image.png](attachment:fa2b14b8-22ac-41a7-b200-5c9626c79930.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 15: **PRACTICE OPPORTUNITY:**

**What it does**

-   **In this practice opportunity, you will become an AI Judge by
    comparing blind responses from two AI models. Complete the following
    tasks:** - **1. Visit Chatbot Arena and start a blind test:
    https://beta.lmarena.ai/** - **2. Ask 3 questions that are
    technical, creative, and funny. For example:** - **Technical:
    "Explain how a blockchain works."** - \*\*Creative: "Write a short,
    heartfelt poem for my mom Laila, for her 74th birthday (put

------------------------------------------------------------------------

## Step 16: TASK 4: SETTING UP API KEYS & SIMPLE TESTING (OPENAI API, CLAUDE, & GEMINI)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 17: To communicate with OpenAI, Google, and Anthropic, we need their respective API keys. You'll need to sign up on each platform and generate a key.

**What it does**

-   **OpenAI:** You likely already have this from previous projects. (
    <https://platform.openai.com/api-keys> ) \* **Google Gemini:** Get
    your key from Google AI Studio. (
    <https://aistudio.google.com/app/apikey> ) \* **Anthropic Claude:**
    Request access and generate a key from the Anthropic Console. (
    <https://console.anthropic.com/> -\> API Keys) As before, store
    these keys securely in your `.env` file:
    `dotenv OPENAI_API_KEY=sk-YourOpenAIKey... GOOGLE_API_KEY=YourGoogleGeminiKey... ANTHROPIC_API_KEY=sk-ant-YourAnthropicKey...`
    Now, let's install the necessary libraries and load the keys.

------------------------------------------------------------------------

## Step 18: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Compare code generation ability of the 3 LLMs covered above
    (Claude Sonnet by Anthropic, gpt-4o by OpenAI, and gemini-2.0-flash
    by Google)** - **Try something like:** - **test_prompt = "Build a
    function that calculates BMI. Let users choose between metric (kg/m)
    and imperial (lb/in) units."**

------------------------------------------------------------------------

## Step 19: TASK 5: DEFINING THE STARTUP IDEA & PROMPT

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 20: We need a consistent prompt to give each AI model. This prompt should clearly state:

**What it does**

1.  The **context** or personality we want the AI to take (e.g., You are
    an expert web developer). 2. The **instruction**: generate HTML code
    for a landing page. 3. The **output indicator** required:
    specifically, the full HTML structure for an `index.html` file.
    Let's define our startup idea and the prompt.

------------------------------------------------------------------------

## Step 21: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Change the `startup_name` and `startup_concept` variables in the
    code cell above to describe a different fictional startup (e.g., "AI
    Recipe Chef" or "Personalized Fitness Planner".** - **Rerun the code
    cell to update the `html_prompt` variable with your new idea.** -
    **Read the updated `html_prompt` to ensure your changes are
    reflected. This new prompt will be used in the following steps.**

------------------------------------------------------------------------

## Step 22: TASK 6: GENERATE HTML LANDING PAGES WITH OPENAI

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 23: Let's start with OpenAI, which we're already familiar with.

**What it does**

We will: 1. Call the `chat.completions.create` method. 2. Use our
`html_prompt` as the user message. 3. Extract the generated HTML
content. 4. Display the generated code. 5. **NEW:** Save the content to
a file named `openai_landing_page.html`.

------------------------------------------------------------------------

## Step 24: **PRACTICE OPPORTUNITY:**

**What it does**

-   **In the code cell above, change the `model` parameter in the
    `openai_client.chat.completions.create` call from `"gpt-4o"` to a
    different OpenAI model you have access to (e.g.,
    `"gpt-4o-mini"`).** - **Rerun the cell and observe the generated
    HTML code. Is it significantly different?** - **Check the saved
    `openai_landing_page.html` file to ensure it was updated. (You might
    need to refresh your file browser).**

------------------------------------------------------------------------

## Step 25: TASK 7: GENERATE HTML LANDING PAGES WITH GOOGLE GEMINI

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 26: Now, let's do the same task using Google Gemini. Notice the slight difference in how we call the API using the `google-generativeai` library.

**What it does**

We will: 1. Call the `generate_content` method on our configured
`gemini_model`. 2. Pass the `html_prompt`. 3. Extract the generated text
(Gemini's response object has a `.text` attribute). 4. Display the
generated code. 5. Save the content to `gemini_landing_page.html`.

------------------------------------------------------------------------

## Step 27: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Look closely at the raw HTML code generated by Gemini in the
    output above (or in the `gemini_landing_page.html` file).** -
    **Compare it to the structure generated by OpenAI (from the previous
    task).** - **Use Google Gemini model to generate an HTML page using
    a different startup and vision (e.g.: Quantum computing startup)**

------------------------------------------------------------------------

## Step 28: TASK 8: GENERATE HTML LANDING PAGES WITH ANTHROPIC CLAUDE

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 29: Finally, let's use Anthropic's Claude. Again, note the API call structure is unique to this provider. We'll use a Claude 3 model like Sonnet or Haiku.

**What it does**

We will: 1. Call the `messages.create` method on the `claude_client`. 2.
Specify the `model` we want to use (e.g., `claude-3-7-sonnet-20250219`).
(Most powerful model from Anthropic) 3. Provide the prompt within the
`messages` list. Claude often works well with a system prompt too,
although our main instructions are in the user message here. 4. Extract
the content from the response (it's usually within
`response.content[0].text`). 5. Display the generated code. 6. Save

------------------------------------------------------------------------

## Step 30: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Modify the prompt to include a `contact/sign-up` form with colors
    that catch attention, feel free to get creative!** - **Rerun all
    three models and open the saved files (`openai_landing_page.html`,
    `gemini_landing_page.html`, `claude_landing_page.html`) in a text
    editor and compare the code structure from all three providers for
    the *same* startup prompt.** - \*\*Which provider do you think
    generated the cleanest, most semantic HTML structure based purely on
    reading the code? Which

------------------------------------------------------------------------

## Step 31: PRACTICE OPPORTUNITY SOLUTIONS

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 32: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Using Vellum, compare the Google Gemini 2.5 Pro model with
    Deepseek-R1 (or the latest version) based on latency, context
    window, cut-off date, and accuracy.**

------------------------------------------------------------------------

## Step 33: ![image.png](attachment:cb5129a1-91c5-42fd-8eb0-03e22c92d98a.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 34: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **In this practice opportunity, you will become an AI Judge by
    comparing blind responses from two AI models. Complete the following
    tasks:** - **1. Visit Chatbot Arena and start a blind test:
    https://beta.lmarena.ai/** - **2. Ask a 3 questions that are
    technical, creative, and funny. For example:** - **Technical:
    "Explain how a blockchain works."** - \*\*Creative: "Write a short,
    heartfelt poem for my mom Laila, for her 74th birthday

------------------------------------------------------------------------

## Step 35: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Compare code generation ability of the 3 LLMs covered above
    (Claude Sonnet by Anthropic, gpt-4o by OpenAI, and gemini-2.0-flash
    by Google)** - **Try something like:** - **test_prompt = "Build a
    function that calculates BMI. Let users choose between metric (kg/m)
    and imperial (lb/in) units."**

------------------------------------------------------------------------

## Step 36: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Change the `startup_name` and `startup_concept` variables in the
    code cell above to describe a different fictional startup (e.g., "AI
    Recipe Chef" or "Personalized Fitness Planner".** - **Rerun the code
    cell to update the `html_prompt` variable with your new idea.** -
    **Read the updated `html_prompt` to ensure your changes are
    reflected. This new prompt will be used in the following steps.**

------------------------------------------------------------------------

## Step 37: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **In the code cell above, change the `model` parameter in the
    `openai_client.chat.completions.create` call from `"gpt-4o"` to a
    different OpenAI model you have access to (e.g.,
    `"gpt-4o-mini"`).** - **Rerun the cell and observe the generated
    HTML code. Is it significantly different?** - **Check the saved
    `openai_landing_page.html` file to ensure it was updated. (You might
    need to refresh your file browser).**

------------------------------------------------------------------------

## Step 38: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Look closely at the raw HTML code generated by Gemini in the
    output above (or in the `gemini_landing_page.html` file).** -
    **Compare it to the structure generated by OpenAI (from the previous
    task).** - **Use Google Gemini model to generate an HTML page using
    a different startup and vision (e.g.: Quantum computing startup**

------------------------------------------------------------------------

## Step 39: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Modify the prompt to include a `contact/sign-up` form with colors
    that catch attention, feel free to get creative!** - **Rerun all
    three models and open the saved files (`openai_landing_page.html`,
    `gemini_landing_page.html`, `claude_landing_page.html`) in a text
    editor and compare the code structure from all three providers for
    the *same* startup prompt.** - \*\*Which provider do you think
    generated the cleanest, most semantic HTML structure based purely on
    reading the code? Which

------------------------------------------------------------------------

## Step 40: ![image.png](attachment:423dabcc-1a00-45d2-85d4-ad3b664b156d.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 41: - **Would love to connect with everyone on LinkedIn: www.linkedin.com/in/dr-ryan-ahmed**

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 42: ![image.png](attachment:1c472849-8781-46be-84a8-5171e5d1c895.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Overall Workflow

``` text
Understand the Problem
        ↓
Install & Import Libraries
        ↓
Prepare Inputs
        ↓
Configure the AI Components
        ↓
Run the Application
        ↓
Review the Output
```

## One-Line Summary

This notebook demonstrates how to build the application step by step,
explaining the purpose of each major section before producing the final
result.
