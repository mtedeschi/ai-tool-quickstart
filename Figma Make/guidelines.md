# Prompting Guidelines
## A. Workflow Rules
* Work in gated steps. After each step, STOP and wait for my signal.
* Proceed only when I reply with one of these tokens (case-sensitive):
    - APPROVE STEP <n> → move to the next step
    - REVISE STEP <n>: <instructions> → make changes and re-submit the same step
    - QUESTIONS STEP <n> → ask up to 5 crisp questions, then STOP
    - SKIP STEP <n> → skip and propose impacts/risks (then STOP)
    - ROLLBACK TO STEP <n> → revert decisions/artifacts to that step (then STOP)

* If anything is ambiguous, ask before building (use QUESTIONS STEP <n>).
* Use the Output Template below at the end of every step.
* Maintain naming conventions and versioning across steps.

## B. Naming & Versioning
* Frames: screen/<area>/<name> (e.g., screen/wizard/step-1-name-duration)
* Components: cmp/<category>/<name> (e.g., cmp/cards/tour-list-card)
* Variants: state=<default|hover|active|error>, size=<sm|md|lg>, lang=<en|ja>
* Styles/Tokens: token/color/*, token/blur/*, token/shadow/*, token/radius/*
* Versions: append v1, v2 on revisions (e.g., cmp/cards/tour-list-card v2)

## C. Output Template (use after every step)
```
STEP <n> – STATUS
What I created:
- Frames:
- Components:
- Styles/Tokens:
Key decisions:
Open questions (if any):
Diff from previous step (bulleted):
Acceptance checklist:
[ ] Matches requirements
[ ] Accessible (WCAG AA color/size)
[ ] Mobile-first, responsive behavior specified
[ ] i18n ready (EN/JA variants or affordances)
[ ] Offline/empty/error states covered (if relevant)
Next action I propose:
-- WAITING FOR: APPROVE STEP <n> / REVISE STEP <n> / QUESTIONS STEP <n> --
```

## D. Constraints to Enforce (every step)
* Platform: PWA, mobile-first, offline-capable.
* APIs: Design for Google Maps (search, directions, tiles).
* i18n: EN/JA; avoid text baked into images; support dynamic label lengths.
* Accessibility: WCAG 2.1 AA (min type sizes, contrast, focus states, touch targets ≥44px).
* Performance: Prefer lightweight effects; note fallbacks if blur/glass is costly.

## E. Review Commands (what I will send)
* APPROVE STEP <n>
* REVISE STEP <n>: <change list>
* QUESTIONS STEP <n>
* SKIP STEP <n>
* ROLLBACK TO STEP <n>