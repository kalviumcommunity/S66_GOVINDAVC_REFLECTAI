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

