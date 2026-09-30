# My Voice — Product Feedback

## 1. Alexa+ simulated experience path

### What did you use it for?
I used the Alexa+ simulated-experience option as the primary track path for My Voice. The prototype demonstrates a voice-capable, context-aware accessibility and advocacy workflow in a browser rather than claiming a deployed Alexa+ add-on.

### What worked well?
The alternate simulation path made it possible to build and demonstrate the interaction model without access to the gated Alexa+ add-on developer tooling.

The rules explicitly allow a simulated Alexa+ experience, which was important because it let the project focus on interaction design, user agency, consent, accessibility, and persistent state rather than pretending to have production Alexa+ integration.

### What needs work?
The relationship between the public hackathon rules, the gated Alexa+ add-on tooling, and the simulation option could be much clearer in one place.

A new participant can easily assume the Category SDK, MCP Toolkit, CLI, or Web Simulator will become available after joining the hackathon. In practice, those tools remain preview-only for selected partners.

The simulation route is valid, but that is easy to miss until reading the FAQ and discussion threads closely.

### Onboarding experience
Getting from zero to a compliant concept required more reading than expected because information about the available Alexa+ paths is split across rules, FAQs, documentation, and discussion replies.

Once the simulation exemption was clear, implementation was straightforward.

### Would you build with Alexa+ again?
**Yes.**

The voice-first and multimodal model is a strong fit for accessibility and personal-support use cases. I would build with Alexa+ again, particularly if hackathon participants had access to a public sandbox or simulator that more closely reflects the production developer experience.

---

## 2. Browser Web Speech Recognition API

### What did you use it for?
Optional microphone input. Users can speak instead of typing when the browser supports speech recognition.

### What worked well?
It allowed the prototype to demonstrate voice-capable input without making speech mandatory. The API is simple to feature-detect and works well enough for a demonstration in supported Chromium environments.

### What needs work?
Support and behaviour are browser-dependent, and speech handling may involve the browser vendor. That makes it unsuitable as the only input path.

The project therefore includes a complete text fallback and clearly states that speech availability depends on the browser.

### Onboarding experience
Very fast. Feature detection and a basic recognition flow were straightforward.

### Would you use it again?
**Yes, as an optional enhancement only.**

I would not make it the sole interaction method for an accessibility-focused product.

---

## 3. Web Storage API (localStorage)

### What did you use it for?
To persist reminders, timeline entries, trusted contacts, accessibility settings, and demo state in the same browser.

### What worked well?
It is simple, fast, offline-friendly, and requires no backend for a hackathon prototype.

It also made it possible to demonstrate returning later and seeing unresolved matters still present.

### What needs work?
localStorage is not secure account storage and is not encrypted. It is also tied to the browser profile and device.

For a production accessibility product, this would need to be replaced with authenticated, secure, encrypted storage with appropriate privacy controls.

### Onboarding experience
Immediate. No configuration was required.

### Would you use it again?
**Yes for prototypes, no for sensitive production data.**

---

## 4. HTML, CSS, and JavaScript browser platform

### What did you use it for?
The complete simulated Alexa+ interface and application logic.

### What worked well?
The browser platform made the prototype easy to run locally, inspect, test, and demonstrate without a build system or package manager.

It also made responsive and accessibility testing straightforward across desktop, tablet, and mobile viewport sizes.

### What needs work?
Browser-level differences remain a concern, especially around speech recognition and some accessibility behaviours.

### Onboarding experience
Very fast because the project has no build step. A local HTTP server is enough to run it.

### Would you use it again?
**Yes.**

For a simulation and interaction prototype, the simplicity and auditability were major advantages.

---

## 5. OpenAI ChatGPT / Codex as development tools

### What did you use them for?
Development assistance, code review, QA planning, defect finding, documentation review, and independent verification of the final browser prototype.

### What worked well?
They were particularly useful for adversarial review: identifying accessibility regressions, misleading claims, unsafe wording, persistence issues, and edge cases in deterministic safety rules.

### What needs work?
AI development assistance still requires strict human review. It can generate plausible but incorrect assumptions if requirements are not tightly constrained.

For this project, all claims were manually narrowed to what the prototype actually does, and the final build was independently exercised through browser checks.

### Onboarding experience
Immediate.

### Would you use them again?
**Yes, with human verification and explicit acceptance criteria.**

They are most useful when treated as development and review tools rather than as an authority.
