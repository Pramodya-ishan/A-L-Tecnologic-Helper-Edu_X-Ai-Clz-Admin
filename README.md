# 🚀 Gemini ETech Controller

A production-grade TypeScript controller for the Google GenAI SDK. This module is designed to power an educational platform with a dual-persona AI: a specialized **Subject Tutor ("Edu_X")** and a human-mimicking **Administrative Assistant**.

## ✨ Key Features

### 🧠 Intelligent Model Cascading
Never fail on a rate limit (`429`) or server overload. This controller implements a recursive fallback chain:
1.  **Tier 1:** `gemini-3-pro-preview` / `gemini-3-flash` (Complex reasoning)
2.  **Tier 2:** `gemini-2.5-pro` / `gemini-2.5-flash` (Stable standard)
3.  **Tier 3:** `gemini-2.0-flash` (Legacy/Fallback)
*If the primary model fails, the system automatically retries with a lighter model without interrupting the user experience.*

### 🎭 Dynamic Personas
The system dynamically injects system instructions based on context:
* **Edu_X (The Tutor):** High-energy, emoji-friendly teaching persona. Supports specific subject constraints (Technology Stream), stress-detection protocols (jokes/motivation), and Socratic teaching methods.
* **Admin (The Human):** Mimics a busy Sri Lankan support agent. Features "Night Mode" (time-aware responses), strict short-text formatting, and direct database verification for payments/IDs.

### 🇱🇰 Localization & Context
* **Language Support:** Native handling of English and Sinhala (Unicode).
* **Cultural Context:** Built-in logic for Sri Lankan exams (A/L), local payment methods, and youth slang/Singlish parsing.

### 🛠️ Advanced Capabilities
* **Tool Use:** Integrated Google Search for finding educational videos (Tutor mode only).
* **Memory Management:** Automatic history trimming to maintain context window efficiency.
* **Stream Stability:** Robust error handling for streaming responses.

## 📦 Installation

```bash
npm install @google/genai