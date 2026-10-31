# Business Requirements Document (BRD)

**Project:** Mental Health Chatbot

This BRD was written for the use case described in the README. The stakeholder roles are fictional. For the detailed functional specification, see the [FRD](FRD.md).

## 1. Document control

| Item | Detail |
|---|---|
| Project | Mental Health Chatbot |
| Project type | Python NLP project |
| Author | Neha Somawanshi |
| Status | Delivered as a working prototype |

## 2. Purpose and scope

**Purpose.** Offer people who are feeling low or stressed a simple, respectful first conversation that recognizes how they feel and points them to coping tips and resources.

**In scope**
- A text chatbot that reads a user's message and detects their emotional tone
- Recognizing the intent behind the message
- Empathetic replies with coping tips and resource suggestions based on the emotional cue
- Modular scripts that are easy to extend

**Out of scope**
- Diagnosis, therapy or medical advice
- Crisis intervention and emergency response
- Long-term user profiles or mood tracking
- Voice interaction

## 3. Stakeholders

| Stakeholder | Role | Interest |
|---|---|---|
| Users | People experiencing low mood or emotional distress | A kind, relevant reply and useful next steps |
| Wellbeing or support team (fictional) | Sponsor | A low-cost way to offer basic first-line support |
| Developer (author) | Builder | A modular design that can be improved over time |

## 4. Business problem and objectives

People who feel low or stressed often have no immediate, judgment-free place to start. A chatbot can offer basic support at any time, but it must respond with care because the topic is sensitive.

| ID | Objective | Success measure |
|---|---|---|
| BO-1 | Provide basic emotional support through conversation | Replies are empathetic and relevant to the user's message |
| BO-2 | Identify the user's sentiment and emotional state | Precision 85%, recall 83%, accuracy 86% |
| BO-3 | Suggest helpful resources and coping strategies based on the user's input | Each emotional cue triggers a matching tip or resource |
| BO-4 | Keep the system easy to extend | Conversation logic split into modular scripts |

## 5. Business requirements

| ID | Requirement | Objective | Priority |
|---|---|---|---|
| BR-1 | The chatbot must understand free-text messages from the user | BO-1 | Must |
| BR-2 | The chatbot must detect the emotional tone of each message | BO-2 | Must |
| BR-3 | The chatbot must recognize what the user wants, such as talking, calming techniques or just sharing | BO-1, BO-3 | Must |
| BR-4 | Replies must use warm, respectful language | BO-1 | Must |
| BR-5 | The chatbot must offer coping tips or resources that match the user's emotional cue | BO-3 | Must |
| BR-6 | The chatbot must reply positively and encouragingly to good moods | BO-1 | Should |
| BR-7 | Conversation logic must be modular and expandable | BO-4 | Should |

## 6. Assumptions and constraints

- The chatbot is a prototype for learning and demonstration, not a clinical tool.
- It is built in Python 3.x with NLTK, and the dependencies include scikit-learn and Flask.
- Emotional tone is detected with rules, and intent is classified with a simple ML model.
- The README does not describe the dataset used to train and test the intent model.

## 7. Risks

| Risk | Impact | Response |
|---|---|---|
| A user in serious distress or crisis uses the chatbot | The user may need more help than the bot can give | The bot is positioned as basic support only; crisis keyword detection and helpline information are recommended next steps |
| Rule-based tone detection misreads a message | An unsuitable or insensitive reply | Noted as a limitation; ML-based sentiment detection is a future improvement |
| Users may treat the bot as a replacement for professional help | Delayed support | Replies encourage reflection and use of resources |
| The model's accuracy (86%) leaves a gap | Some messages are misclassified | Continue testing on more messages |

## 8. Acceptance criteria

- The chatbot runs from `chatbot.py` and replies to typed messages.
- A low-mood message gets an empathetic reply that offers to talk or suggests calming techniques.
- A positive message gets an encouraging reply.
- Tone detection and intent classification are reported with precision, recall and accuracy.
- Conversation logic is split into separate scripts.

---

Back to the [project README](README.md).
