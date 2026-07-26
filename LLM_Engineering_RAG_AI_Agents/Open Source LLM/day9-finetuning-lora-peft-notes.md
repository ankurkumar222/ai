# Open Source LLM Fine-Tuning Using PEFT + LoRA

## Notebook Walkthrough (Easy Language)

## Big Picture

This notebook teaches an open-source **Gemma** model to classify the
**sentiment of financial news**.

Overall flow:

``` text
Load Dataset
    ↓
Prepare Data
    ↓
Test Base Model (Zero-Shot)
    ↓
Fine-Tune using LoRA
    ↓
Evaluate Again
    ↓
Compare Results
```

------------------------------------------------------------------------

# Step 1: Understand the Problem

**Goal**

Teach an LLM to classify financial news into:

-   Positive
-   Negative
-   Neutral

Example:

  News                             Sentiment
  -------------------------------- -----------
  Company reports record profits   Positive
  Company files for bankruptcy     Negative
  Annual meeting was held          Neutral

Nothing is trained here. This section only explains the problem.

------------------------------------------------------------------------

# Step 2: Install & Import Libraries

Installs required libraries such as:

-   transformers
-   datasets
-   peft
-   trl
-   accelerate
-   bitsandbytes

Think of this as:

> "Collecting all the tools before starting."

After installation, the notebook imports them into Python.

------------------------------------------------------------------------

# Step 3: Check GPU

The notebook checks whether a GPU is available.

Why?

Training an LLM on a CPU is extremely slow.

If a GPU is available: - Faster training - Faster inference

------------------------------------------------------------------------

# Step 4: Load the Dataset

Downloads a Financial News dataset.

Each row contains:

-   News text
-   Sentiment label

Example:

  News                   Label
  ---------------------- ----------
  Tesla stock jumps      Positive
  Company reports loss   Negative

------------------------------------------------------------------------

# Step 5: Explore the Dataset

The notebook checks:

-   Number of rows
-   Columns
-   Sample records
-   Label names

Purpose:

Make sure the dataset loaded correctly.

------------------------------------------------------------------------

# Step 6: Convert to Pandas

Converts the Hugging Face dataset into a Pandas DataFrame.

Reason:

Pandas makes the data easier to inspect and manipulate.

------------------------------------------------------------------------

# Step 7: Split Train and Test Data

The dataset is divided into:

-   Training data (\~80%)
-   Testing data (\~20%)

Training teaches the model.

Testing checks how well it learned.

------------------------------------------------------------------------

# Step 8: Convert Data into Chat Format

Gemma is a **chat model**, so the notebook converts each example into a
conversation.

Instead of:

News → Positive

It becomes:

``` text
System:
You are a financial sentiment classifier.

User:
Tesla stock jumps after earnings.

Assistant:
Positive
```

This is the format the model understands.

------------------------------------------------------------------------

# Step 9: Check the Formatting

Prints one or two formatted examples.

Purpose:

Verify the conversion worked correctly.

------------------------------------------------------------------------

# Step 10: Learn Evaluation Metrics

Introduces:

-   Accuracy
-   Precision
-   Recall
-   F1 Score
-   Confusion Matrix

These metrics are used later to measure performance.

------------------------------------------------------------------------

# Step 11: Test the Base Model (Zero-Shot)

Downloads the original Gemma model.

No training yet.

The notebook simply asks:

> "Read this news and predict Positive, Negative or Neutral."

These predictions become the **baseline**.

------------------------------------------------------------------------

# Step 12: Create Prompts

Builds prompts such as:

``` text
System:
You are a financial sentiment classifier.

User:
Apple announces layoffs.

Answer only:
Positive
Negative
Neutral
```

The model receives this prompt for every test example.

------------------------------------------------------------------------

# Step 13: Evaluate the Base Model

Compares:

Actual labels

vs

Predicted labels

Then calculates:

-   Accuracy
-   Precision
-   Recall
-   F1 Score

This tells us how good the original model is.

------------------------------------------------------------------------

# Step 14: Configure LoRA (PEFT)

This is the main part of the notebook.

Instead of updating **every weight** inside the model,

LoRA trains only a **very small set of adapter weights**.

Think of it like:

Without LoRA

``` text
Modify the entire model
```

With LoRA

``` text
Freeze the original model
+
Train only small adapters
```

Advantages:

-   Less GPU memory
-   Faster training
-   Smaller checkpoints

------------------------------------------------------------------------

# Step 15: Train the Model

Uses **SFTTrainer**.

The trainer repeatedly:

1.  Reads a training example
2.  Generates a prediction
3.  Calculates the error
4.  Updates only the LoRA adapters

This repeats for all batches until training finishes.

------------------------------------------------------------------------

# Step 16: Load the Fine-Tuned Model

After training, the notebook loads:

Base Model

-   

LoRA Adapters

Now the model has learned from the financial dataset.

------------------------------------------------------------------------

# Step 17: Evaluate Again

Runs the same test dataset again.

Calculates:

-   Accuracy
-   Precision
-   Recall
-   F1 Score

Now these numbers represent the **fine-tuned model**.

------------------------------------------------------------------------

# Step 18: Compare Results

Finally compares:

``` text
Before Fine-Tuning
        ↓
Zero-Shot Accuracy

vs

After Fine-Tuning
        ↓
LoRA Fine-Tuned Accuracy
```

This shows whether fine-tuning improved performance.

------------------------------------------------------------------------

# Notebook Summary

``` text
Start
   │
   ▼
Understand the Problem
   │
   ▼
Install Libraries
   │
   ▼
Load Financial Dataset
   │
   ▼
Explore Dataset
   │
   ▼
Train/Test Split
   │
   ▼
Convert to Chat Format
   │
   ▼
Load Base Gemma Model
   │
   ▼
Zero-Shot Predictions
   │
   ▼
Measure Baseline Accuracy
   │
   ▼
Configure LoRA
   │
   ▼
Fine-Tune Model
   │
   ▼
Load Fine-Tuned Model
   │
   ▼
Evaluate Again
   │
   ▼
Compare Results
   │
   ▼
Done
```

## One-Line Summary

This notebook demonstrates how to **fine-tune a Gemma language model for
financial sentiment classification using PEFT + LoRA**, then compares
its performance before and after fine-tuning.
