# Build a Calorie Tracker

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

## Step 1: TASK 1: PROJECT OVERVIEW

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 2: ![image.png](attachment:ea0bda5c-aeb8-4863-bc31-c0b6c6d3e2c3.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 3: ![image.png](attachment:7d4ac6c7-f5be-4889-86da-aab22d73e647.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 4: ![image.png](attachment:4027c8d2-ecd7-43e1-a0e8-40a6bcf1510a.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 5: TASK 2.LET'S READ A SAMPLE IMAGE

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 6: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Download another food image (e.g., a banana, a slice of pizza) and
    save it to your project folder. Update the `image_filename` variable
    in the code cell above to the new filename and run the cell again.
    Does it load and display correctly?** - **Look at the printed output
    for the `Format`, `Size`, and `Mode` of your images.**

------------------------------------------------------------------------

## Step 7: TASK 3. UNDERSTAND PROMPT ENGINEERING FUNDAMENTALS

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 8: ![image.png](attachment:88777eba-4458-4840-95ea-05033585fe5c.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 9: ![image.png](attachment:323a88b4-2c94-4e59-ae09-b4f5bae81dbb.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 10: ![image.png](attachment:7d23d512-a404-4a60-85e3-43b9ae748d1d.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 11: ![image.png](attachment:32edfb90-e6fe-4ede-b262-dd0ed3eab1dd.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 12: ![image.png](attachment:d9e349ad-96e2-4006-81d1-55b3754f6649.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 13: **PRACTICE OPPORTUNITY:**

**What it does**

-   **BlackRock private equity investment firm receives financial
    reports, earnings call transcripts, and analyst notes on potential
    portfolio companies. The goal is to automate the extraction of key
    financial metrics, market sentiment, and strategic risks. You have
    received an earnings call transcript for a potential acquisition
    company, "SolidPower Inc.".** - \*\*Draft a prompt that classifies
    the CEO's tone as optimistic, cautious, or concerning based on key
    phrases. Design the prompt

------------------------------------------------------------------------

## Step 14: TASK 4. LET'S PERFORM IMAGE RECONGITION USING OPENAI'S VISION API

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 15: Let the magic begin!

**What it does**

Let's send our loaded image to OpenAI's GPT Vision model and ask a
simple question: "What food is in this image?" OpenAI requires images to
be sent either as a URL or as a base64-encoded string. We'll use base64
encoding for local files. The image is part of the `messages` list.

------------------------------------------------------------------------

## Step 16: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Modify the `food_recognition_prompt` variable in the code above.
    Ask a different question, like
    `"What is the main color of the food in this image?"` or
    `"Is this food likely sweet or savory?"`. Run the cell again and
    perform a sanity check on OpenAI's API response.**

------------------------------------------------------------------------

## Step 17: TASK 5. LET'S OBTAIN THE NUMBER OF CALORIES USING VISION API

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 18: **PRACTICE OPPORTUNITY:**

**What it does**

-   **Modify the `structured_nutrition_prompt` to include more fields
    (e.g. sugar_grams or fiber_grams)** - **Try using an image of pizza
    slice (simple) or a complex dish (like a mixed salad) or a packaged
    food item. How well does OpenAI's API estimate nutritional value? Do
    they lower their confidence level?**

------------------------------------------------------------------------

## Step 19: PRACTICE OPPORTUNITY SOLUTIONS

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 20: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Download another food image (e.g., a banana, a slice of pizza) and
    save it to your project folder. Update the `image_filename` variable
    in the code cell above to the new filename and run the cell again.
    Does it load and display correctly?** - **Look at the printed output
    for the `Format`, `Size`, and `Mode` of your images.**

------------------------------------------------------------------------

## Step 21: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **BlackRock private equity investment firm receives financial
    reports, earnings call transcripts, and analyst notes on potential
    portfolio companies. The goal is to automate the extraction of key
    financial metrics, market sentiment, and strategic risks. You have
    received an earnings call transcript for a potential acquisition
    company, "SolidPower Inc.".** - \*\*Draft a prompt that classifies
    the CEO's tone as optimistic, cautious, or concerning based on key
    phrases. Design the prompt

------------------------------------------------------------------------

## Step 22: \`\`\`text

**What it does**

Context: You are a senior financial analyst with expertise in private
equity. Instruction: Carefully review the provided earnings call
transcript of Solid Power. Based on the language, sentiment, and key
financial and operational signals shared by the CEO, classify the CEO's
tone as one of the following: Optimistic, Cautious, or Concerning. Your
analysis should identify specific language cues, strategic outlooks, and
underlying business sentiment. Input: "Operator: Good morning, and
welcome

------------------------------------------------------------------------

## Step 23: \`\`\`text

**What it does**

Expected output Tone Classification: Optimistic Key Supporting Evidence:
"I'm pleased to share our results for Q4 2024 and our outlook for the
year ahead." -- The CEO opens with a confident and upbeat tone, setting
the stage for positive news. "Solid Power posted strong revenue growth
of 8.2% year-over-year, reaching \$420 million for the quarter." --
Describes revenue growth as "strong" and highlights consistent
performance with nine consecutive quarters of

------------------------------------------------------------------------

## Step 24: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Modify the `food_recognition_prompt` variable in the code above.
    Ask a different question, like
    `"What is the main color of the food in this image?"` or
    `"Is this food likely sweet or savory?"`. Run the cell again and
    perform a sanity check on OpenAI's API response.**

------------------------------------------------------------------------

## Step 25: **PRACTICE OPPORTUNITY SOLUTION:**

**What it does**

-   **Modify the `structured_nutrition_prompt` to include more fields
    (e.g. sugar_grams or fiber_grams)** - **Try using an image of pizza
    slice (simple) or a complex dish (like a mixed salad) or a packaged
    food item. How well does OpenAI's API estimate nutritional value? Do
    they lower their confidence level?**

------------------------------------------------------------------------

## Step 26: ![image.png](attachment:2efeab11-937e-4c4c-81db-c0e11cf0f32f.png)

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 27: - **Would love to connect with everyone on LinkedIn: www.linkedin.com/in/dr-ryan-ahmed**

**What it does**

This section introduces the next stage of the notebook.

------------------------------------------------------------------------

## Step 28: ![image.png](attachment:599c4221-1f20-4ddc-b18e-fcc855aa2fc9.png)

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
