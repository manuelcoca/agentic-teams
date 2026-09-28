---
name: write-sdd
description: Write a software design description (SDD) for one structured piece using IEEE 1016 viewpoints and C4 component views. Use when defining schema, interfaces, runtime steps, or scaling before implementation.
user-invocable: true
disable-model-invocation: false
---

# Write an SDD

An SDD is the **building blueprint** for one piece. It builds upon the
available requirements, such as EARS functional statements and a requirements
specification; it replaces neither.

Read [references/ieee-1016.md](references/ieee-1016.md) when choosing
views. Copy structure from [assets/sdd-template.md](assets/sdd-template.md).

## Where to write

Do not assume a path.

1. Use the path given by the invoking agent, prompt, or user.
2. Else search for an existing SDD for this piece (headings such as
   `SDD`, `Software design description`, or IEEE 1016 view names).
   Update that file, or add a sibling in the same directory.
3. Else ask where the design description should go.

## When this skill applies

Run when the change has structure: a new store or schema, a new
protocol, a new module boundary, or scaling and failure rules for this
piece.

Skip for a requirement change inside an existing module that needs no new
structure. The existing requirements are enough.

## Procedure

1. Read the available requirements and the current system map.
2. Read matching decision records. Do not reopen them.
3. Write only the IEEE 1016 views this piece needs. Keep the design aligned
   with those requirements without repeating them.
4. Draw C4 component or dynamic diagrams only where a list of parts is
   not enough.
5. If a new container appears, the system-wide architecture description is
   stale. Stop and update it first.
6. Do not use the SDD to introduce a new requirement. Put functional behavior
   in the functional requirements and additional qualities or imposed
   constraints in the requirements specification.

## Do not

- Repeat requirements as design
- Document the whole product
- Choose among alternatives here; that belongs in a decision record
- Specify function-level code or file-by-file edits
- Document historical context, changes, features, and decisions. Always only contain the current state.
