# Pregnancy Chatbot

The **Pregnancy Chatbot** is an interactive tool designed to provide pregnancy and infant care-related information to users. It supports personalized responses based on the user's pregnancy stage and offers helpful nudges and insights. This chatbot is built as a terminal-based application and acts as a foundation for future enhancements, including human-in-the-loop escalation and deployment scalability.

---

## Features

### 1. **QnA Chat**
- Responds to frequently asked questions about pregnancy and infant care.
- Provides personalized responses based on the user's pregnancy stage.

### 2. **Onboarding**
- Collects essential user details such as:
  - Name.
  - Pregnancy stage (e.g., 1st trimester, 2nd trimester).
  - Preferred language.
- Stores user information in a `user_data.json` file for personalized interactions.

### 3. **Nudges**
- Offers proactive suggestions based on the pregnancy stage:
  - **1st Trimester**: "Remember to take folic acid supplements daily and stay hydrated!"
  - **2nd Trimester**: "Consider light exercises like walking or yoga to stay active."
  - **3rd Trimester**: "Prepare your hospital bag and discuss your birth plan with your doctor."

### 4. **Analytics**
- Logs user interactions in an `analytics.json` file.
- Tracks queries, responses, and errors (if any) for usage analysis.

### 5. **Human-in-the-Loop Escalation** *(Planned)*
- Outlines a process to escalate unresolved queries to human experts.

---

## Project Structure

```
pregnancy-chatbot/
├── bot/
│   ├── escalation/
│   │   └── human_in_the_loop.md     # Documentation for escalation process
│   ├── nudges/
│   │   └── nudges.py                # Nudges module for proactive suggestions
│   ├── onboarding/
│   │   ├── onboarding_flow.py       # Onboarding process implementation
│   │   └── onboarding.md            # Documentation for onboarding flow
│   ├── analytics.py                 # Logs user interactions for analysis
│   ├── mock_responses.py            # Mock responses for QnA
│   ├── qna_chatbot.py               # Main chatbot script
│   ├── flowchart.md                 # Flowchart documentation
│   └── __init__.py                  # Makes `bot/` a Python module
├── user_data.json                   # Stores user details (generated during onboarding)
├── analytics.json                   # Logs user queries and responses
└── README.md                        # Project documentation
```

---

## Getting Started

### Prerequisites
1. **Python 3.8 or higher** installed on your system.
2. A terminal or command-line interface to interact with the chatbot.

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/jhansilakshmi27/pregnancy-chatbot.git
   ```
2. Navigate to the project directory:
   ```bash
   cd pregnancy-chatbot
   ```

---

## Usage

### Step 1: Run the Onboarding Flow
Before using the chatbot, run the onboarding script to provide your details:
```bash
python3 bot/onboarding/onboarding_flow.py
```
- Enter your name, pregnancy stage (e.g., `1st trimester`), and preferred language.

### Step 2: Interact with the Chatbot
Start the chatbot to ask questions and receive personalized responses:
```bash
python3 bot/qna_chatbot.py
```
- Example queries:
  - **"How can I deal with morning sickness?"**
  - **"Is it safe to exercise during pregnancy?"**
- Type `exit` to end the session.

### Step 3: Check Analytics Logs
Interactions are logged in the `analytics.json` file for analysis:
```json
[
    {
        "timestamp": "2025-04-22 18:55:33",
        "user_name": "chiki",
        "query": "How can I deal with morning sickness?",
        "response": "You can manage morning sickness by eating small, frequent meals, staying hydrated, and avoiding strong odors. Ginger or peppermint tea can also help.",
        "error": null
    }
]
```

---

## Modules

### 1. **QnA Chatbot (`qna_chatbot.py`)**
- Main script to interact with the chatbot.
- Retrieves responses from `mock_responses.py` based on user queries.

### 2. **Mock Responses (`mock_responses.py`)**
- Stores predefined responses for common queries.
- Example:
  ```python
  mock_responses = {
      "morning sickness": "You can manage morning sickness by eating small, frequent meals, staying hydrated, and avoiding strong odors. Ginger or peppermint tea can also help.",
      ...
  }
  ```

### 3. **Onboarding Flow (`onboarding_flow.py`)**
- Collects user details, including name, pregnancy stage, and preferred language.
- Saves the data in `user_data.json`.

### 4. **Nudges Module (`nudges.py`)**
- Provides proactive suggestions tailored to the user's pregnancy stage.

### 5. **Analytics Module (`analytics.py`)**
- Logs user interactions (queries, responses, and errors) for analysis.

### 6. **Escalation Documentation (`human_in_the_loop.md`)**
- Describes the process for escalating unresolved queries to human experts.

