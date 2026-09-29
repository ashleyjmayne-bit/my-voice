# My Voice — Judge Pitch

## 30-second version
“Most technology for vulnerable people is designed to help somebody else look after them.

My Voice is different. It is an Alexa+ companion built for the person themselves.

It helps someone understand confusing information, remember what matters, recognise suspicious requests and communicate what they want — while preserving their exact words and requiring explicit consent before anything is shared.

The core design is simple: **What you said. What I understood. What do you want done?**

The goal is not to monitor vulnerable people. It is to give them more agency.”

## 60-second version
“Many elderly, disabled and vulnerable adults live in a world where other people increasingly speak for them — family, carers, providers and support services.

My Voice uses Alexa+ to give some of that control back.

A user can ask for a letter to be explained, save questions for an appointment, check whether a suspicious request has warning signs, or explain a concern in their own words.

The important part is what happens next.

My Voice never silently replaces the user’s words with an AI summary. It shows three things separately: **what you said, what I understood, and what you want done.**

The user can keep something private in this browser, save it, prepare a message or explicitly confirm a simulated share with someone they trust.

The prototype includes persistent same-browser state, intent routing, document fact extraction, weighted risk analysis, consent gates and a local decision record for key workflow checks and state changes.

We are not trying to build technology that watches vulnerable people more closely. We are trying to build technology that listens to them better.”

## Likely judge questions

### Why Alexa+?
Voice can be more accessible than a conventional app interface for people with limited mobility, vision, dexterity or digital confidence. The production concept uses Alexa+ as a conversational layer while keeping user-controlled state and consent rules in a secure backend. This hackathon entry demonstrates that interaction model as a simulated Alexa+ browser experience.

### Why not just use a chatbot?
My Voice is not presented as a general chatbot. The prototype maintains same-browser state, routes requests into defined workflows, extracts key facts, tracks unresolved items, applies explicit consent gates and records key workflow decisions.

### Why deterministic logic instead of an LLM?
For the hackathon prototype, deterministic logic makes the demo reproducible, transparent and free to run. A production system could use a language model for broader language understanding while keeping consent, permissions, sharing and critical safety boundaries deterministic and auditable.

### How do you reduce the risk of the system getting the user’s meaning wrong?
The user’s exact wording is preserved separately from the system interpretation. The person can revise their original words and rerun the workflow before deciding what happens next.

### Does My Voice automatically report abuse or contact anyone?
No. Sharing is simulated in the prototype and always requires an explicit final confirmation from the user.

### What is the commercial path?
Potential future users and partners could include aged-care providers, disability-support organisations, advocacy services, community-health organisations, families and accessibility platforms. Any real deployment would need secure cloud storage, proper authentication, privacy controls and the relevant Alexa+ development access and certification.
