---
paths:
  - "apps/web/**"
  - "**/components/**"
---

# Frontend & design-system rules

- Prefer existing design-system components over custom UI.
- New design-system components or public API changes require tech-lead approval.
- Interactive flows must be keyboard accessible; forms need labels and error text.
- Feature-flag new user-facing behaviour; default OFF.
- Colocate or follow existing test patterns (React Testing Library).
- Do not add new dependency packages without human approval.
