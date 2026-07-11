# Usage

```go
package main

import (
	"context"
	"fmt"

	"github.com/go-instagram/instagram"
)

func main() {
	// A sessionid cookie is usually required for reads to succeed.
	c := instagram.New(instagram.WithSessionID("your-sessionid-cookie"))

	prof, err := c.UserProfile(context.Background(), "instagram")
	if err != nil {
		panic(err) // 401/403/429 here means Instagram is blocking the request.
	}
	fmt.Printf("%s (%s) — %d followers\n", prof.FullName, prof.Username, prof.Followers)
	for _, p := range prof.Posts {
		fmt.Printf("- %s  %d likes  %s\n", p.Permalink, p.Likes, p.Caption)
	}
}
```

Unauthenticated requests are frequently rejected; you will usually need a valid logged-in `sessionid` cookie (`WithSessionID`). A `401`/`403`/`429` here means Instagram is blocking the request — not a bug in the code.

For the complete, always-current API — every type and field — see
[pkg.go.dev/github.com/go-instagram/instagram](https://pkg.go.dev/github.com/go-instagram/instagram).
