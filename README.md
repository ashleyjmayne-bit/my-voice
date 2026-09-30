# My Voice

**Your voice. Your words. Your choice.**

My Voice is a browser-based **simulated Alexa+ accessibility and advocacy companion** created for the **Alexa+ track of Amazon Build, Ship, Shape 2026**.

It is designed for elderly, disabled, cognitively impaired, or otherwise vulnerable adults who may benefit from a simpler way to understand everyday information, remember important matters, communicate in their own words, recognise suspicious requests, and choose whether to share something with a trusted person.

## Demo

**Public demo video:** https://www.youtube.com/watch?v=9KmDy0o6oiM

The demo is 1:45 and shows the working prototype, including the explicit consent flow for simulated trusted-contact sharing.

## Core interaction model

**What you said → What I understood → What do you want done?**

The user's original words remain separate from the system's interpretation, and nothing is shared automatically.

## Run the prototype

No build step, package manager, paid API, or account is required.

From the repository folder:

```bash
python -m http.server 4173
```

Then open:

`http://127.0.0.1:4173/index.html`

A current Chromium-based browser is recommended.

## What the prototype includes

- Help me understand
- Remember this
- Help me say this
- Something doesn't feel right
- Tell someone I trust
- What am I still waiting on?
- Trusted contacts
- Accessibility settings
- Hackathon Demo mode
- Browser speech recognition where supported, with complete text fallback
- Persistent same-browser state using `localStorage`
- Deterministic intent routing
- Structured fact extraction
- Weighted safety/risk rules
- Explicit consent before simulated sharing

## Architecture

This is a **simulated Alexa+ experience**, not a deployed Alexa+ add-on.

The current prototype is deliberately deterministic and browser-local. It does not use a paid AI API, does not send real messages, and does not perform real bank, email, medical, legal, emergency, or identity-verification actions.

See [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md).

## Accessibility

The prototype includes:

- larger text options;
- high-contrast mode;
- reduced-motion support;
- keyboard-visible focus;
- skip navigation;
- accessible labels and live regions;
- responsive layouts tested at desktop, tablet, and mobile sizes.

## Privacy and safety boundaries

- No automatic sharing.
- No automatic speech output.
- No external application network requests.
- Same-browser local storage only; it is not encrypted cloud storage.
- Browser speech recognition depends on browser support and may involve the browser vendor's speech service.
- Safety checks are heuristic and do not verify identity.
- The prototype is not medical, legal, financial, or emergency advice.

## Review status

Independent technical review completed on 30 September 2026:

- 39/39 browser checks passed
- static integrity check passed
- 0 console errors
- 0 unexpected outbound requests
- desktop, tablet, and mobile layouts checked
- reload persistence passed

Detailed evidence is in [`qa/`](qa/).

## Submission materials

Final submission materials are in [`docs/`](docs/), including:

- final Devpost submission copy
- Product Feedback
- friction log
- feature requests
- architecture notes
- judge pitch
- demo video script

## Licence

Released under the MIT License for hackathon review and reuse.
