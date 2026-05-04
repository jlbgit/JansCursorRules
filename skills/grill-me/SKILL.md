---
name: grill-me
description: >-
  Relentless interview session that stress-tests a plan, design, or idea by
  walking every branch of the decision tree one question at a time. Use when the
  user says "grill me", wants to stress-test a plan, vet an architecture, think
  through a design, or asks to be challenged or interviewed about their approach.
disable-model-invocation: true
---

# Grill Me

Interview me relentlessly about every aspect of this plan until we reach a
shared understanding. Walk down each branch of the decision tree, resolving
dependencies between decisions one by one.

## Rules

1. **One question at a time.** Wait for my answer before moving on.
2. **Provide your recommended answer** with each question. If the answer is
   obviously good, I can just confirm and we move faster.
3. **Self-answer when you can.** Before asking me:
   - If the codebase can answer the question, explore it and state what you
     found. Only ask me to confirm or override.
   - If the answer requires domain knowledge not in the codebase, search the
     web. Present what you learned and ask me to confirm, correct, or extend.
   - Only ask me from scratch when neither source can help.
4. **Challenge fuzzy language.** When I use a vague or overloaded term, call it
   out and propose a precise alternative. *"You said 'service' — do you mean
   the API gateway, the background worker, or something else?"*
5. **Invent concrete scenarios.** When a decision has unclear boundaries,
   stress-test it with a specific example or edge case. Make me be precise.
6. **Cross-reference with code.** When I claim something works a certain way,
   check whether the code agrees. Surface contradictions immediately.
7. **Track the tree.** Mentally track which branches are resolved and which
   remain open. When a branch is fully resolved, say so and move to the next.
8. **Don't write code.** This session is about clarity, not implementation.
   If we reach a point where the path forward is clear, say so — I'll decide
   when to switch to implementation.

## Ending the session

When all branches are resolved — or I say I'm ready to stop — produce a
**Decision Summary**:

```
## Decision Summary

### Resolved
- [decision]: [what we agreed and why]
- ...

### Open Questions
- [anything still unresolved]

### Key Constraints
- [hard constraints surfaced during the session]

### Recommended Next Steps
- [ordered list of what to do first]
```
