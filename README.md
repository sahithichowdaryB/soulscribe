# SoulScribe

SoulScribe is an emotionally-aware journaling app designed to support personal growth, emotional reflection, and mental well-being. Built using Flutter for the frontend and a backend powered by Python and modern cloud platforms, SoulScribe leverages LLMs (Large Language Models) and a personalized Mood Context Processor (MCP) to guide and affirm users through their journaling journey.

---

## 🚀 Features

### 🔐 1. User Authentication

* Login/Register using **Firebase Auth** (email or anonymous)
* Each user gets a unique `userID`, used across:

  * Journal entries
  * Mood tagging
  * MCP personalization

### 📝 2. Guided Journal Entry

* Personalized writing prompts fetched from an LLM
* First-time users get a gentle, general prompt
* Returning users receive context-aware prompts based on their mood and writing history
* User writes freely and optionally tags their mood

### 💾 3. Save Entry to Database

* Entries stored with metadata in Firestore or Supabase

```json
{
  "userID": "abc123",
  "timestamp": "2025-05-19T21:00:00Z",
  "entryText": "I was feeling low but grateful.",
  "mood": "anxious",
  "tags": ["work stress", "tired", "hope"]
}
```

### 🔁 4. MCP Context Update

* Backend analyzes the last 5–10 journal entries

* Extracts insights such as:

  * Mood trends
  * Emotional trajectory
  * Recurring themes
  * Writing tone
  * Preferred reflection styles

* Stores a JSON context object per user

### 📤 5. LLM Reflection Generation

* Upon saving, the backend sends a custom prompt to the LLM based on:

  * Today’s journal
  * MCP insights
* LLM returns an affirmation or reflective response

#### Example Prompt:

```
You are SoulScribe, an emotionally aware journaling companion.

Here’s what we know:
- The user frequently reflects on stress, emotional resilience, and gratitude.
- Their writing style is introspective and they prefer gentle encouragement.
- They’ve been journaling consistently for the past 7 days.
- Mood pattern: anxious → reflective → hopeful.

Today’s entry:
“I was feeling low but grateful.”

Please generate a short, poetic reflection that supports healing and affirms growth.
```

#### Example Output:

> “Even in low places, you've managed to find light. That’s not just gratitude — that’s grace. Keep holding onto it.”

### 📲 6. Flutter UI Experience

* Clean, minimal interface
* Writing screen with floating prompts
* Affirmation card shown after saving

### 📈 7. Future Scope: Visualization & Trends

* Mood timeline graphs
* Word cloud for tags/themes
* Journal frequency insights
* Visualized using `fl_chart`, `pie_chart`, or custom animations

### 🔔 8. Future Scope: Notifications (Optional)

* Daily journaling reminders
* Context-aware notifications powered by MCP:

  * "You've shown great emotional strength this week — how are you today?"

### 🌐 9. Deployment & Sharing

| Component | Platform                  |
| --------- | ------------------------- |
| Frontend  | Flutter (Web/APK/iOS)     |
| Hosting   | Firebase Hosting / GitHub |
| Backend   | Render / Railway / Fly.io |
| Demo      | Live Link or Recording    |

---

## 📦 Tech Stack

* **Flutter** (Cross-platform frontend)
* **Firebase** / **Supabase** (Auth + DB)
* **Python** Backend for MCP + LLM Prompting
* **OpenAI GPT-4** (LLM prompt & response)
* **VS Code / Android Studio**

---

## 🤝 Contributing

We're building SoulScribe as a mindful tool for emotional wellness. If you’re passionate about Flutter, AI, or mental health, contributions are welcome!

---


