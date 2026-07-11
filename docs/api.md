# API reference

Source-verified against [`go-instagram/instagram`](https://github.com/go-instagram/instagram). The
authoritative, versioned reference is
[pkg.go.dev/github.com/go-instagram/instagram](https://pkg.go.dev/github.com/go-instagram/instagram).

## Constructor & methods

| Symbol | Purpose |
|---|---|
| `New(...Option) *Client` | Construct a client. |
| `(*Client).UserProfile(ctx, username) (*Profile, error)` | Fetch a public profile and its recent posts. |

## Options

Functional options passed to `New`:

| Option | Purpose |
|---|---|
| `WithSessionID(sessionID)` | Send a `sessionid` cookie for authenticated reads (usually required). |
| `WithBaseURL(url)` | Override the request origin (defaults to `https://www.instagram.com`). |
| `WithHTTPClient(*http.Client)` | Supply a custom HTTP client (timeouts, proxy, transport). |
| `WithUserAgent(ua)` | Set the `User-Agent` header. |

## Result types

| Type | Purpose |
|---|---|
| `Profile` | A profile (`FullName`, `Username`, `Followers`, `Posts`, …). |
| `Post` | A single post (`Permalink`, `Likes`, `Caption`, …). |

!!! note
    This table is a map, not the contract. Field-level details live in the
    [package reference](https://pkg.go.dev/github.com/go-instagram/instagram) and the
    repository's `README`.
