---
name: write-srs
description: Write or review an ISO/IEC/IEEE 29148 software requirements specification (SRS) covering functional, quality, performance, security, interface, regulatory, technical, and imposed architectural requirements. Use when asked for an SRS or for requirements of any kind.
user-invocable: true
disable-model-invocation: false
---

# Write an SRS

An SRS states what the system must do and how well it must do it. Every
requirement in it is written as an EARS statement with an acceptance check.

## Read first

- The existing requirements for the capability, when they exist
- [29148 characteristics](./references/29148-and-ears.md)
- [SRS template](./assets/srs-template.md)

## Artifact ownership

The invoking task owns the destination, change lifecycle, and relationship to
other project artifacts. Use the path it provides. Ask when no destination is
provided; do not invent a folder convention in this skill.

## Procedure

1. Name the capability, its actors, and its scope.
2. Add stakeholders, definitions, non-goals, or rationale only when they are
   needed to interpret a requirement.
3. Write the functional requirements: the behavior a user, client, operator, or
   external system can observe.
4. Write the remaining requirements the capability needs:
   - measurable quality, performance, capacity, availability, and reliability;
   - security, privacy, regulatory, and organizational constraints;
   - external API, protocol, file-format, and interoperability requirements;
   - imposed technical or architectural constraints.
5. Give each requirement a stable ID, one EARS statement, and at least one
   objective acceptance check.
6. Add explanatory prose only when a term, boundary, rationale, or measurement
   scope would otherwise be unclear.
7. Review each requirement against the 29148 characteristics. Ask when a need
   is unclear; do not invent targets or constraints.
8. Put preferred design in a design description, architecture description, or
   decision record rather than in a requirement.

## Structure rule of thumb

Group SRS documents by stable capability rather than by feature branch,
package, class, or individual command. Keep one SRS per capability and use a
small index when a product has several capabilities.

## 29148 bar

Necessary, implementation-free, unambiguous, singular, verifiable,
traceable. Full list in the reference.

## Do not

- Put implementation steps, folders, classes, or shell commands in a requirement
- Put several needs in one sentence
- Turn a preferred design into an architectural requirement
- Store user stories as a second requirements list
- Write architecture or design in this file
- Document historical context, changes, features, and decisions. Always only contain the current state.

## Done when

- [ ] Every requirement is an EARS statement with a stable ID.
- [ ] Every requirement has at least one objective acceptance check.
- [ ] Explanatory prose exists only where it resolves ambiguity.
- [ ] No preferred design or implementation step is stated as a requirement.
- [ ] Open questions identify missing decisions without inventing answers.
