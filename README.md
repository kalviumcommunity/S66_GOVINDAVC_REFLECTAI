# 🌟 ReflectAI — Smart Journaling Assistant

**ReflectAI** is an intelligent journaling assistant that helps users reflect on inspirational quotes by turning them into personalized reflection prompts. This project combines the power of large language models with practical software design concepts, including **Prompting**, **RAG (Retrieval-Augmented Generation)**, **Structured Output**, and **Function Calling**.

---

## 🧠 Project Overview

The goal of ReflectAI is to enhance mindfulness, journaling, and self-awareness through automated, AI-generated reflections. The user inputs an inspirational quote, and the system:

- Identifies the **core theme** (e.g., resilience, gratitude, growth)
- Generates a **deep reflection question** aligned with the theme
- Suggests a **positive affirmation**
- Recommends a **small action step**
- Provides options to **save the entry**, **set a reminder**, or **export it**

ReflectAI is useful for individuals, therapists, life coaches, and educators aiming to foster consistent introspection and personal growth.

---

## 💡 Key AI Concepts Implemented

### 🔹 1. Prompting

We use carefully engineered prompts to guide the language model (e.g., GPT-4) to:

- Extract the central **theme** from the user-provided quote.
- Generate a **reflective question** relevant to that theme.
- Suggest a matching **affirmation** and an **actionable step**.

**Example System Prompt:**

This ensures consistent, high-quality generation focused on emotional and mental well-being.

---

### 🔹 2. Structured Output

All AI-generated content is returned in a **predefined JSON format**, which includes:

```json
{
  "quote": "The only limit to our realization of tomorrow is our doubts of today.",
  "theme": "Self-belief",
  "personal_reflection_prompt": "When did self-doubt hold you back, and how might you overcome it next time?",
  "affirmation": "I believe in my ability to shape a better future.",
  "suggested_action": "Write down one doubt you have and reframe it into a positive belief."
}

## 🛠️ Prompt Design (RTFC Framework)

As part of this task, we created both **System** and **User** prompts for ReflectAI using the **RTFC framework** (Role, Task, Format, Constraints):

- **System Prompt** → Defined the assistant’s role as a *mindful journaling coach* that extracts the theme, reflection, affirmation, and action step from any inspirational quote.  
- **User Prompt** → Instructs the assistant to analyze a given quote and return outputs in structured **JSON** format.  
- **RTFC Applied** →  
  - **R (Role):** ReflectAI as a journaling assistant  
  - **T (Task):** Analyze quotes and generate reflection outputs  
  - **F (Format):** Consistent JSON output  
  - **C (Constraints):** Keep responses mindful, positive, and concise  

This ensures ReflectAI consistently produces **high-quality, structured, and safe outputs** for journaling and self-reflection.


## 🎯 Zero-Shot Prompting

In this task, we explored **Zero-Shot Prompting** to guide ReflectAI in generating journaling outputs directly from quotes without any prior examples.

### 🔹 What is Zero-Shot Prompting?
Zero-shot prompting is when we ask a model to perform a task **without providing it with example inputs or outputs**.  
Instead, the model relies entirely on its **pre-trained knowledge** and the clarity of the instructions we give.

This approach tests the model’s ability to **generalize instructions** and respond accurately to new tasks it hasn’t explicitly seen before.

---

### 🔹 Zero-Shot Prompt Used
Here is an inspirational quote:
"Do what you can, with what you have, where you are."

Analyze the quote and provide:

The central theme

A reflective journaling question

A positive affirmation

A small actionable step

Return the response strictly in JSON format.

---

### 🔹 How We Utilized It in ReflectAI
- We gave the model **only task instructions**, without showing any examples.  
- The model used its **internal knowledge of language and context** to extract a theme, question, affirmation, and action.  
- This helps ensure ReflectAI can work with **any inspirational quote**, even if it has not seen similar quotes before.  

By applying zero-shot prompting, ReflectAI stays flexible and adaptive while keeping outputs **structured, useful, and consistent**.



## 🎯 One-Shot Prompting

In this task, we explored **One-Shot Prompting** for ReflectAI. Unlike zero-shot prompting, here we provide the model with **one example** of the task before asking it to generate new outputs.

### 🔹 What is One-Shot Prompting?
One-shot prompting is when we give the model **a single input–output example** to guide its behavior.  
This helps the model understand the **desired format, tone, and style** before producing its own response.

---

### 🔹 One-Shot Prompt Used
Example:
Quote: "The only limit to our realization of tomorrow is our doubts of today."

Output (JSON):
{
"quote": "The only limit to our realization of tomorrow is our doubts of today.",
"theme": "Self-belief",
"personal_reflection_prompt": "When did self-doubt hold you back, and how might you overcome it next time?",
"affirmation": "I believe in my ability to shape a better future.",
"suggested_action": "Write down one doubt you have and reframe it into a positive belief."
}

Now analyze the following quote:

"Do what you can, with what you have, where you are."

Return the response in the same JSON format.

---

### 🔹 How We Utilized It in ReflectAI
- We first gave the model **a single worked-out example** of how to analyze a quote and generate outputs.  
- Then, we asked it to apply the **same pattern** to a new quote.  
- This improves consistency in output structure and helps ReflectAI stay closer to the desired journaling tone.  

By applying one-shot prompting, ReflectAI combines **clarity of instruction** with **a concrete example**, making its outputs more reliable and predictable.




## 🎯 Multi-Shot Prompting

In this task, we explored **Multi-Shot Prompting** for ReflectAI.  
This approach provides the model with **multiple examples** before asking it to generate a new output.  

### 🔹 What is Multi-Shot Prompting?
Multi-shot prompting is when we supply the model with **two or more input–output examples** to guide its behavior.  
By showing several examples, the model can better learn the **pattern, structure, and tone** expected in the responses, which improves accuracy and reliability.

---

### 🔹 Multi-Shot Prompt Used
Example 1:
Quote: "The only limit to our realization of tomorrow is our doubts of today."

Output (JSON):
{
"quote": "The only limit to our realization of tomorrow is our doubts of today.",
"theme": "Self-belief",
"personal_reflection_prompt": "When did self-doubt hold you back, and how might you overcome it next time?",
"affirmation": "I believe in my ability to shape a better future.",
"suggested_action": "Write down one doubt you have and reframe it into a positive belief."
}

Example 2:
Quote: "Happiness depends upon ourselves."

Output (JSON):
{
"quote": "Happiness depends upon ourselves.",
"theme": "Self-responsibility",
"personal_reflection_prompt": "What choices can you make today that bring you closer to genuine happiness?",
"affirmation": "I have the power to create my own happiness.",
"suggested_action": "List three small actions you can take today that bring you joy."
}

Now analyze the following quote:

"Do what you can, with what you have, where you are."

Return the response in the same JSON format.

---

### 🔹 How We Utilized It in ReflectAI
- We gave the model **multiple examples** (instead of one) so it clearly learns the pattern.  
- This helps ensure **consistency in JSON formatting** and **better alignment with journaling tone**.  
- With multi-shot prompting, ReflectAI becomes more reliable for production use, as it generalizes from examples more effectively.  

By applying multi-shot prompting, ReflectAI achieves **greater stability and accuracy**, making it suitable for real-world journaling applications.
