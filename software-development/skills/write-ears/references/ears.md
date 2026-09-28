# EARS pattern examples

The Easy Approach to Requirements Syntax (EARS) was introduced by Alistair
Mavin and colleagues at the INCOSE International Symposium in 2009.

## Patterns

### Ubiquitous

Use for behavior that always applies.

> The system shall preserve the selected language between sessions.

### Event-driven

Use when an event triggers the response.

> When the reviewer submits a supported image, the system shall start an
> analysis for that image.

### State-driven

Use while a defined state holds.

> While an analysis is processing, the system shall show its processing state.

### Optional

Use when behavior applies only when a feature or configuration exists.

> Where summary export is enabled, the system shall provide the summary as a
> downloadable file.

### Unwanted

Use for invalid input, failures, abuse, or other unwanted conditions.

> If the uploaded file is empty, then the system shall reject the upload.

### Complex

Use when a requirement needs more than one keyword. Keep the clause order.

> While an analysis is processing, when the reviewer cancels it, the system
> shall stop the analysis.

## Source

- Alistair Mavin et al., "Easy Approach to Requirements Syntax (EARS)", INCOSE International Symposium, 2009