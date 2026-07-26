# An Adaptive LLM-Based AI Tutor with Gradio Interface for Multi-Level Learning

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

## Step 1: TASK 1: PROJECT OVERVIEW - ADAPTIVE AI TUTOR

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 2: ![image.png](attachment:b7687d7c-3a78-409d-8549-ddf8a4bb610b.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 3: ![image.png](attachment:ce1db3cc-8aad-4ad2-a4eb-7ba2f4c41d53.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 4: ![image.png](attachment:ed4a2174-cb7c-406c-b997-8297bddf1063.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 5: TASK 2: INSTALL GRADIO AND SET UP OPENAI API KEY (REFRESHER)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 6: ![image.png](attachment:ee105c9a-0299-489a-8319-80c60de15aef.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 7: - **Gradio Link: https://www.gradio.app/**

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 8: Just like before, our AI Tutor needs to talk to the OpenAI API. To do this, it requires your secret API key.

**What it does**

**Reminder:** We store keys securely in a `.env` file. Make sure you
have a file named `.env` in the same directory as this notebook with
your key:
`dotenv OPENAI_API_KEY=sk-YourSecretOpenAIKeyGoesHereXXXXXXXXXXXXX`
Let's load the key and set up the OpenAI client.

------------------------------------------------------------------------

## Step 9: TASK 3: BUILD A BASIC AI TUTOR FUNCTION (NO GRADIO YET)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 10: Before we build the user interface, let's create the core Python function that will act as our AI Tutor.

**What it does**

This function will: 1. Take a user's `question` as input. 2. Construct a
prompt for the OpenAI API, telling it to act as a helpful tutor. 3. Call
the OpenAI API. 4. Return the AI's answer.

------------------------------------------------------------------------

## Step 11: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Change the `test_question` variable to ask about a different topic
    (e.g., "What is photosynthesis?", "Explain the concept of gravity.",
    "Summarize the plot of Hamlet.").** - **Run the code cell above
    again to see how the AI Tutor responds to your new question.** -
    **Can you change "helpful and patient AI Tutor" personality defined
    in the `system_prompt` to the opposite, i.e.: make it "impatient and
    unhelpful AI tutor"?!**

------------------------------------------------------------------------

## Step 12: TASK 4: BUILD AN INTERACTIVE INTERFACE USING GRADIO

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 13: Now for the exciting part! Let's use **Gradio** to wrap our `get_ai_tutor_response` function in a simple web interface.

**What it does**

**Core Gradio Concept:** `gr.Interface` The `gr.Interface` class is the
main way to build UIs in Gradio. You tell it: \* `fn`: The Python
function to call (our `get_ai_tutor_response`). \* `inputs`: What kind
of input component(s) the user will use (e.g., a text box). We use
`gr.Textbox()`. \* `outputs`: What kind of output component(s) will
display the result (e.g., another text box). We use `gr.Textbox()`. \*
`title`, `description`: Optional text to

------------------------------------------------------------------------

## Step 14: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Modify the `title` argument in the `gr.Interface` call above to
    something different, like " 🤖 My Awesome AI Explainer".** -
    **Change the `description` to provide different instructions.** -
    **Experiment with the `inputs` textbox: Change `lines=2` to
    `lines=5` to make the input box taller.** - \*\*Rerun the code cell
    that defines and launches the interface to see your changes take
    effect. (Note: You might need to stop the previous Gradio

------------------------------------------------------------------------

## Step 15: TASK 5: ADD STREAMING FOR AN ENHANCED CHAT EXPERIENCE

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 16: You might have noticed that you have to wait until the AI finishes generating the entire response before you see anything. For longer answers, this can feel slow.

**What it does**

We can improve this using "streaming". Just like we learned with the
OpenAI API directly, we can process the response chunk-by-chunk as it
arrives. Gradio natively supports Python generator functions for
streaming output to text boxes! **Steps:** 1. Modify our AI interaction
function to use `stream=True` in the OpenAI API call. 2. Make the
function a generator by using `yield` to return each chunk of text as it
comes in,

------------------------------------------------------------------------

## Step 17: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Think of a question that likely requires a multi-paragraph answer
    (e.g., "Explain in detail how electric vehicles work", "What are the
    key differences between Python 2 and Python 3?").** - **Ask this
    question in both the non-streaming interface (from Task 4, if you
    still have it running or relaunch it) and the streaming interface
    (from Task 5).** - \*\*Compare the user experience. How does the
    delay feel in the

------------------------------------------------------------------------

## Step 18: TASK 6: ADDING AN EXPLANATION LEVEL SLIDER

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 19: Our AI Tutor is helpful, but what if the user needs a *simpler* explanation, or perhaps a more *in-depth* one? We can add a control for this!

**What it does**

Gradio provides various input components. Let's use a `gr.Slider` to let
the user choose an explanation level. **Steps:** 1. Define a mapping
from slider values (e.g., 1 to 5) to descriptive levels ("like I'm 5",
"like I'm 10", "high school", "college", "expert"). 2. Modify our
streaming function to accept this `level` as an additional input. 3.
Inside the function, use the selected level to modify the system prompt
sent to

------------------------------------------------------------------------

## Step 20: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Ask the AI Tutor to explain a concept you know reasonably well
    (e.g., "What is the internet?", "How does a car engine work?"). Try
    getting explanations at levels 1, 3, and 5. Has the AI successfully
    adjusted its explanation style?** - \*\*Look at the
    `explanation_levels` dictionary and add a new level (e.g., make
    level 6 "with Ph.D. level Einstein mad scientist"). Relaunch the
    interface and test if this change

------------------------------------------------------------------------

## Step 21: PRACTICE OPPORTUNITY SOLUTIONS

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 22: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Change the `test_question` variable to ask about a different topic
    (e.g., "What is photosynthesis?", "Explain the concept of gravity.",
    "Summarize the plot of Hamlet.").** - **Run the code cell above
    again to see how the AI Tutor responds to your new question.** -
    **Can you change "helpful and patient AI Tutor" personality defined
    in the `system_prompt` to the opposite, i.e.: make it "impatient and
    unhelpful AI tutor"?!**

------------------------------------------------------------------------

## Step 23: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Modify the `title` argument in the `gr.Interface` call above to
    something different, like " 🤖 My Awesome AI Explainer".** -
    **Change the `description` to provide different instructions.** -
    **Experiment with the `inputs` textbox: Change `lines=2` to
    `lines=5` to make the input box taller.** - \*\*Rerun the code cell
    that defines and launches the interface to see your changes take
    effect. (Note: You might need to stop the previous Gradio

------------------------------------------------------------------------

## Step 24: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Think of a question that likely requires a multi-paragraph answer
    (e.g., "Explain in detail how electric vehicles work", "What are the
    key differences between Python 2 and Python 3?").** - **Ask this
    question in both the non-streaming interface (from Task 4, if you
    still have it running or relaunch it) and the streaming interface
    (from Task 5).** - \*\*Compare the user experience. How does the
    delay feel in the

------------------------------------------------------------------------

## Step 25: The streaming version provided a smoother, more interactive user experience. Even though both gave the same answer, the streaming version felt faster and more human-like.

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 26: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Ask the AI Tutor to explain a concept you know reasonably well
    (e.g., "What is the internet?", "How does a car engine work?"). Try
    getting explanations at levels 1, 3, and 5. Has the AI successfully
    adjusted its explanation style?** - \*\*Look at the
    `explanation_levels` dictionary and add a new level (e.g., make
    level 6 "with Ph.D. level Einstein mad scientist"). Relaunch the
    interface and test if this change

------------------------------------------------------------------------

## Step 27: ![image.png](attachment:f67942f8-80e7-410d-85fb-7b99c240e521.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 28: - **Would love to connect with everyone on LinkedIn: www.linkedin.com/in/dr-ryan-ahmed**

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 29: ![image.png](attachment:78036e11-fa5d-4a6d-aa51-07c3752d729e.png)

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
