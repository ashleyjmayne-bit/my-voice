# My Voice — Final Devpost Submission Copy

## Project name
My Voice

## Tagline
Your voice. Your words. Your choice.

## Primary track
Alexa+

## Short description
My Voice is a simulated Alexa+ accessibility and advocacy companion designed for elderly, disabled, cognitively impaired, and otherwise vulnerable adults. It helps a person understand everyday information, remember unresolved matters, express concerns in their own words, recognise suspicious requests, and choose whether to share something with someone they trust.

The core interaction is:

**What you said → What I understood → What do you want done?**

The person’s exact words are always kept separate from the system’s interpretation, and nothing is shared automatically.

## Inspiration
A lot of technology for vulnerable people is designed around monitoring, supervising, or informing carers and family members.

My Voice starts from the opposite direction: build for the person themselves.

The idea is simple. A person may receive a confusing bill, forget what they needed to follow up, struggle to explain a concern, or feel uncomfortable about a suspicious request. They should be able to ask for help without losing control of their own words or choices.

My Voice is designed to listen first.

## What it does
My Voice provides six core workflows:

1. **Help me understand** — extracts important facts from a letter, bill, form, or message and explains them plainly.
2. **Remember this** — keeps a follow-up or concern on the person’s list until they decide it is finished.
3. **Help me say this** — preserves the person’s exact words, then shows a separate neutral interpretation before asking what they want done.
4. **Something doesn’t feel right** — checks for warning signs such as requests for passwords, PINs, unusual payments, urgency, remote access, or impersonation.
5. **Tell someone I trust** — requires the person to choose a trusted contact, review their exact words, and explicitly confirm before a simulated share.
6. **What am I still waiting on?** — keeps unresolved matters visible across sessions in the same browser.

The prototype also includes a personal timeline, trusted contacts, accessibility controls, keyboard support, optional speech input, and a guided hackathon demo.

## How we built it
This submission uses the official **simulated Alexa+ experience** path permitted by the hackathon rules.

The prototype is a browser-based application built with HTML, CSS, and JavaScript. It is deliberately deterministic and browser-local so the behaviour shown in the demo is reproducible and easy for judges to inspect.

Key implementation details:

- deterministic intent routing;
- structured fact extraction;
- weighted safety rules;
- exact-word preservation separate from interpretation;
- explicit consent before simulated sharing;
- same-browser persistence through localStorage;
- optional browser speech recognition with full text fallback;
- accessibility settings for text size, high contrast, reduced motion, keyboard focus, skip navigation, and responsive layouts.

The current hackathon build does not claim to be a deployed Alexa+ add-on. It simulates the Alexa+ interaction model in a browser because the gated Alexa+ add-on tooling is not available to hackathon participants.

## Challenges we ran into
The biggest challenge was designing a system that helps without quietly taking control away from the user.

That affected almost every part of the build:

- preserving exact user wording instead of silently rewriting it;
- separating interpretation from action;
- making consent visible and explicit;
- ensuring a safety warning does not pretend to verify someone’s identity;
- avoiding automatic sharing;
- keeping the interface usable at large text sizes and high contrast;
- providing a complete text fallback when browser speech recognition is unavailable.

A second challenge was the Alexa+ development environment itself. The public hackathon path supports a simulated Alexa+ experience because the add-on developer tools remain gated. We therefore built and clearly labelled a browser simulation rather than claiming access to tools we did not have.

## Accomplishments we are proud of
The strongest part of My Voice is not a single feature. It is the interaction model:

**What you said → What I understood → What do you want done?**

That structure keeps the person’s own words visible and prevents the system from quietly converting an interpretation into an action.

We also built explicit consent into trusted-contact sharing, a cautious safety workflow that avoids false claims of identity verification, persistent unresolved-item tracking, and accessibility controls that were tested across desktop, tablet, and mobile layouts.

The final reviewed prototype passed 39/39 browser checks with zero console errors and zero unexpected outbound requests.

## What we learned
Accessibility is not just larger text and bigger buttons.

For this project, accessibility also meant:

- preserving agency;
- making system interpretation visible;
- showing what will happen before it happens;
- avoiding hidden sharing;
- allowing corrections;
- giving users a reliable text fallback;
- making the interface understandable without technical language.

We also learned that a simulated Alexa+ experience can still demonstrate a meaningful interaction model when the simulation is clearly labelled, reproducible, and honest about its boundaries.

## What's next
A production version would require secure cloud storage, authenticated accounts, stronger natural-language processing, audited safety logic, and a real messaging layer with explicit consent.

With production Alexa+ developer access, the same interaction model could become a voice-first Alexa+ experience while retaining the same core rules: preserve the person’s words, explain what the system understood, and never act without the person’s choice.

## Technical boundaries
This hackathon prototype:

- is a simulated Alexa+ experience;
- does not use a production Alexa+ add-on;
- does not send real messages;
- does not access bank accounts or email;
- does not provide medical, legal, financial, or emergency decisions;
- does not automatically report abuse;
- does not passively record;
- does not use encrypted cloud storage;
- uses browser-local localStorage for demo persistence;
- uses optional browser speech recognition where supported.

## Repository
https://github.com/ashleyjmayne-bit/my-voice

## Demo video
[ADD PUBLIC YOUTUBE OR VIMEO URL HERE]
