# Functional Requirements Document (FRD)

**Project:** Mental Health Chatbot

This FRD describes how the chatbot meets the requirements in the [BRD](BRD.md).

## 1. Document control

| Item | Detail |
|---|---|
| Project | Mental Health Chatbot |
| Author | Neha Somawanshi |
| Language and libraries | Python 3.x, NLTK, scikit-learn, Flask |
| Entry point | `chatbot.py` |
| Related document | [BRD](BRD.md) |

## 2. System overview

```
User message -> Preprocessing -> Tone detection -> Intent recognition
             -> Response generation -> Resource or coping tip -> Reply
```

## 3. Functional requirements

| ID | Requirement | BR |
|---|---|---|
| FR-1 | Accept a free-text message from the user | BR-1 |
| FR-2 | Preprocess the message: tokenization and stop word removal | BR-1 |
| FR-3 | Detect the emotional tone with a rule-based analyzer | BR-2 |
| FR-4 | Classify the user's intent with a simple ML model | BR-3 |
| FR-5 | Choose a reply based on the detected tone and intent | BR-3, BR-4 |
| FR-6 | Use empathetic wording in every reply | BR-4 |
| FR-7 | Add a personalized coping tip or resource suggestion based on the emotional cue | BR-5 |
| FR-8 | Reply to positive messages with an encouraging response | BR-6 |
| FR-9 | Keep tone detection, intent classification and response logic in separate modules | BR-7 |
| FR-10 | Start the chatbot by running `python chatbot.py` | BR-1 |

## 4. Data requirements

| ID | Requirement |
|---|---|
| DR-1 | Input is plain text typed by the user |
| DR-2 | Text is cleaned and split into tokens before analysis |
| DR-3 | Training data for the intent model must be documented (not yet described in the README) |
| DR-4 | Reply templates and coping tips are stored so they can be edited without changing the core logic |

## 5. Conversation behavior

| Situation | Expected behavior |
|---|---|
| User expresses low mood | Acknowledge the feeling, reassure the user they are not alone, and offer to talk or share calming techniques |
| User expresses a good mood | Respond positively and encourage the mood |
| User asks for coping help | Offer a coping tip or resource that matches the emotional cue |

## 6. Non-functional requirements

| ID | Requirement |
|---|---|
| NFR-1 | Language must always be respectful and non-judgmental |
| NFR-2 | The chatbot must reply quickly enough for a natural conversation |
| NFR-3 | Dependencies are installed with `pip install -r requirements.txt` |
| NFR-4 | New intents or replies can be added without rewriting existing modules |

## 7. Validation checks

| ID | Check | Expected result |
|---|---|---|
| T-1 | Send "I'm feeling really low today." | Empathetic reply that offers to talk or share calming techniques |
| T-2 | Send "I'm actually in a good mood!" | Positive, encouraging reply |
| T-3 | Send an emotional message and check for a tip or resource | A matching coping tip or resource is included |
| T-4 | Evaluate the models on test messages | Precision about 85%, recall about 83%, accuracy about 86% |
| T-5 | Run `python chatbot.py` after installing requirements | Chatbot starts without errors |

## 8. Known limitations

- Rule-based tone detection can misread nuance in sensitive messages.
- The chatbot does not detect crisis language or give emergency contacts. These are recommended future improvements.
- The chatbot is not a substitute for professional mental health support.

## 9. Traceability

| Business requirement | Functional requirements |
|---|---|
| BR-1 | FR-1, FR-2, FR-10 |
| BR-2 | FR-3 |
| BR-3 | FR-4, FR-5 |
| BR-4 | FR-5, FR-6 |
| BR-5 | FR-7 |
| BR-6 | FR-8 |
| BR-7 | FR-9, NFR-4 |

---

Back to the [project README](README.md) or the [BRD](BRD.md).
