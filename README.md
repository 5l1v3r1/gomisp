# gomisp [![](https://godoc.org/github.com/dutchcoders/gomisp?status.svg)](http://godoc.org/github.com/dutchcoders/gomisp) [![Go Report Card](https://goreportcard.com/badge/dutchcoders/gomisp)](https://goreportcard.com/report/dutchcoders/gomisp) 

Golang client for MISP. The client currently only implements search, but it is easy to extend other features.

## Usage

```
package misp

import (
	"fmt"

	misp "github.com/dutchcoders/gomisp"
)

func ExampleExamples_output() {
	client, err := misp.New(
		misp.WithURL("{url}"),
		misp.WithKey("{key}"),
	)
	if err != nil {
		panic(err.Error)
	}

	qry := misp.NewSearchRequest().Value(so.Query).From(time.Now().Add(time.Hour * 24 * 365 * -1)).To(time.Now())

	result, err := client.Search(qry)
	if err != nil {
		panic(err)
	}

	fmt.Printf("Search results: %s\n", result)
}
```

## Contributors

* [Remco Verhoef](https://twitter.com/remco_verhoef)

## Copyright and license

Code released under [Apache License 2.0](LICENSE).

