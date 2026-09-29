# Devpost Submission — My Voice

## Tagline
**Your voice. Your words. Your choice.**

## Inspiration
Many technologies for elderly, disabled and vulnerable people are designed around families, carers or service providers. They help other people monitor, organise or make decisions around the person.

We wanted to build something for the person themselves.

My Voice is designed to help someone understand everyday information, remember what matters, communicate what they want, and ask for help when something does not feel right — without taking control away from them.

## What it does
My Voice is a simulated Alexa+ companion with six core workflows:

1. **Help me understand** — explains letters, bills, appointment messages and instructions in plain English while extracting key dates and actions.
2. **Remember this** — stores questions, concerns and reminders until the user decides they are resolved.
3. **Help me say this** — preserves the user’s exact words, separately shows what the system understood, and asks what the user wants done.
4. **Something doesn’t feel right** — analyses potentially unsafe requests such as credential requests, remote-access demands or unusual payment pressure.
5. **Tell someone I trust** — lets the user choose what to share and with whom, with an explicit final consent step.
6. **What am I still waiting on?** — maintains unresolved items across refreshes in the same browser so the user does not need to start again during the demonstration.

The central interaction model is:

**What you said → What I understood → What do you want done?**

That design is intentional. The user’s own words remain distinct from any machine interpretation.

## How we built it
The prototype is a working simulated Alexa+ experience built as a responsive web application.

The current prototype includes:

- browser-based voice input where supported, with complete text fallback (speech handling depends on the browser);
- intent routing across the product’s major workflows;
- structured information extraction from everyday documents;
- weighted safety/risk analysis for suspicious requests;
- persistent state using local browser storage;
- explicit consent gates before simulated sharing;
- a local decision record for workflow analyses, consent and list-state changes;
- trusted-contact management;
- accessibility settings including larger text, high contrast, reduced motion and selected simpler home-screen wording;
- a judge-facing demo mode that exercises the full workflow.

The current prototype deliberately uses deterministic local logic rather than paid AI APIs. This keeps the demo reproducible, transparent and free to run.

## How Alexa+ fits
Alexa+ is valuable here because the intended users may find conventional app interfaces difficult, tiring or inaccessible.

In a production implementation, Alexa+ could provide the conversational layer while a secure backend maintained preferences, unresolved items, trusted contacts, consent decisions and optional authorised integrations. That implementation has not been built. Alexa+ add-on tooling is currently limited to selected partners and requires certification and on-device testing.

Account linking would use OAuth. Sensitive data would never be accessed without explicit permission, and no contact would receive automatic access.

The hackathon prototype uses a simulated Alexa+ web experience so the full interaction model can be demonstrated without requiring gated preview hardware or paid services.

## Challenges we ran into
The largest design challenge was avoiding the common mistake of building a monitoring system for vulnerable people.

We had to keep asking: **who is actually in control?**

That led to three design rules:
- the person’s original words are always preserved;
- machine interpretation is shown separately;
- nothing important is shared or acted on without explicit consent.

We also avoided claiming capabilities that the prototype does not have. It does not diagnose medical conditions, verify a caller’s identity, contact emergency services autonomously or access bank accounts.

## Accomplishments we are proud of
The strongest part of My Voice is not a single AI feature. It is the interaction model.

A person can say something in their own words, see the system’s separate interpretation, revise their original words and run the check again if needed, and then choose what happens next.

We believe that is a better foundation for assistive AI than systems that automatically speak or act on someone’s behalf.

## What we learned
Assistive technology is not automatically empowering.

A system can be technically impressive and still reduce autonomy if it observes, interprets or escalates without consent.

We learned that the most important technical feature in this product is not automation — it is **user-controlled next steps, visible reasoning and reversible list status**.

## What’s next
A production version could add:
- Alexa+ account linking;
- authorised email/document ingestion;
- secure cloud persistence;
- optional trusted-contact messaging;
- multilingual support;
- integrations with accessibility and support-service ecosystems.

Those would only be added where the user explicitly enables them.

## Built with
- HTML / CSS / JavaScript
- Responsive web UI
- Browser speech recognition where available
- Local persistent state
- Deterministic intent routing
- Structured fact extraction
- Weighted risk analysis
- Consent and audit-state engine

## Accessibility and privacy
My Voice is designed for large text, low cognitive load, keyboard use, high-contrast viewing and reduced motion.

Nothing is shared automatically.

My Voice helps users understand and communicate. It does not replace medical, legal, financial or emergency services.
