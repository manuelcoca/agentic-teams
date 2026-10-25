---
name: write-ears
description: Write requirement statements using the Easy Approach to Requirements Syntax (EARS). Use when writing, rewriting, or reviewing shall-statements in EARS form.
user-invocable: true
disable-model-invocation: false
---

# Write EARS

EARS is a sentence syntax for requirements. Each statement follows a fixed
clause order, so the condition, the system, and the response are always in
the same place.

See [pattern examples](./references/ears.md).

## Structure

```
While <precondition>, when <trigger>, the <system name> shall <system response>.
```

- zero or more preconditions (`While`);
- zero or one trigger (`When`);
- exactly one system name;
- one or more system responses after `shall`.

Clauses always appear in this order.

## Patterns

| Pattern | Keyword | Form |
| --- | --- | --- |
| Ubiquitous | none | The `<system name>` shall `<system response>`. |
| Event-driven | When | When `<trigger>`, the `<system name>` shall `<system response>`. |
| State-driven | While | While `<precondition>`, the `<system name>` shall `<system response>`. |
| Optional feature | Where | Where `<feature is included>`, the `<system name>` shall `<system response>`. |
| Unwanted behavior | If / then | If `<trigger>`, then the `<system name>` shall `<system response>`. |

Complex requirements combine keywords in the same order:

```
Where <feature>, while <precondition>, when <trigger>, the <system name> shall <system response>.
```

## Steps

1. Name the system that owns the response.
2. Decide whether the requirement always applies, starts with an event,
   holds during a state, depends on a feature, or handles an unwanted
   condition.
3. Pick the matching pattern. Use the simplest one that fits.
4. Write the trigger or precondition as a concrete, observable condition.
5. Write the response as what the system does, after `shall`.
6. Read it back: one system, clauses in order, no vague words.