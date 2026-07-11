# Fragility & Terms of Service

!!! danger "Read this before depending on the library"
    Instagram does not offer these endpoints as a stable, documented public API. They are the internal endpoints its own website calls, and they change, rate-limit, and lock without notice.

Instagram does **not** offer these endpoints as a stable, documented public API. They are the internal endpoints its own website calls, and they change, rate-limit, and lock without notice. The response shape can change at any time, which surfaces as decode errors.

## What this means in practice

- Unauthenticated requests are frequently rejected; you will often need a valid logged-in **`sessionid`** cookie (`WithSessionID`).
- Any request can start returning **401 / 403 / 429** at any time when Instagram decides to block you — the library surfaces those as clear errors that mention the status.
- The Go API is deliberately small and stable so your code survives the churn; the transport underneath may break regardless.

## Your responsibility

Automated access to Instagram may violate its Terms of Service and/or
applicable law. **You are responsible for how you use this library** — use it
only for content and in ways you are authorised to access, and respect rate
limits. The maintainers cannot promise the underlying transport keeps working.
