# go-instagram

Pure-Go best-effort read client for public Instagram content.

!!! warning "Best-effort — read [Fragility & ToS](fragility.md) first"
    Instagram does not offer these endpoints as a stable, documented public API. They are the internal endpoints its own website calls, and they change, rate-limit, and lock without notice.

A pure-Go, dependency-free, **best-effort** read client for public Instagram content served through Instagram's web JSON endpoints. The Go API is kept deliberately small and stable so your code can survive the churn underneath — the underlying transport may break at any time regardless.

## Install

```sh
go get github.com/go-instagram/instagram
```

## At a glance

- **CGO-free** (`CGO_ENABLED=0`), Go 1.26+ — builds for every 64-bit target.
- **Zero third-party dependencies** — standard library only.
- **Read-only** — this is a read client; it does not post or mutate.
- BSD-3-Clause.

See [Usage](usage.md) for a runnable example and [API reference](api.md) for the
full surface. The canonical, always-current reference is
[pkg.go.dev](https://pkg.go.dev/github.com/go-instagram/instagram).
