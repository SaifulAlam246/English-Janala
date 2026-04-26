# 📘 English Janala | Project Requirements

---

## 🌐 1. API Architecture
| Action | Endpoint URL |
| :--- | :--- |
| **All Levels** | `https://openapi.programming-hero.com/api/levels/all` |
| **Words by Level** | `https://openapi.programming-hero.com/api/level/{id}` |
| **Word Details** | `https://openapi.programming-hero.com/api/word/{id}` |
| **Full Database** | `https://openapi.programming-hero.com/api/words/all` |

---

## 🛠 2. Core Functional Requirements

### 🎴 Vocabulary Display
- **Initial State:** Show a default welcome/instruction text in the section.
- **Dynamic Loading:** Fetch and display words from **API-02** upon clicking a lesson button.
- **Card UI:** Each card must include:
  - The Word
  - Meaning & Pronunciation
  - Primary Action Buttons (as per Figma)
- **Empty States:** Display **"No Word Found"** if the lesson contains no data.

### 🔘 Navigation & UX
- **Active States:** Highlight the currently selected lesson button with a distinct color.
- **Feedback:** Implement a **Loading Spinner** for all API fetch operations.
- **Data Integrity:** Silently handle invalid data (falsy, `null`, or `undefined`) to prevent UI crashes.

### 🔍 Search & Storage
- **Live Search:** Implement an input box that filters words in real-time.
- **Reset Logic:** Automatically clear the "Active" lesson button state when a search is initiated.
- **Saved Box:** - Add a `Heart Icon` to each word card.
  - On click, store the word in a dedicated **Saved Box** section.

### 🔊 Speech & Details
- **Detail Modal:** Open a modal (data from **API-03**) showing pronunciation, examples, and synonyms.
- **Completion:** Include a "Complete Learning" button to close the modal.
- **Text-to-Speech:** Implement the voice pronunciation trigger using:
  ```js
  function pronounceWord(word) {
    const utterance = new SpeechSynthesisUtterance(word);
    utterance.lang = "en-EN";
    window.speechSynthesis.speak(utterance);
  }