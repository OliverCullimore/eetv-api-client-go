[![License](https://img.shields.io/github/license/OliverCullimore/eetv-client?style=for-the-badge)](https://github.com/OliverCullimore/eetv-client)

# EETV Client

Client for EETV Boxes API written in Go

### Install
```
go get github.com/olivercullimore/eetv-client
```

### Example
main.go

```
package main

import (
	"fmt"
	"log"

	"github.com/olivercullimore/eetv-client"
)

func main() {
	var eetvBaseURL = "" // Enter http://EETVBOXIP/ filling in the EETVBOXIP with the IP of your EETV Box
	var eetvAppKey  = "" // leave this blank usually

	// Init EETV API with config
	eetvAPI = eetv.New(eetvBaseURL, eetvAppKey)

	// Get EETV Box Info
	eetvInfo, err := eetvAPI.GetInfo()
	if err != nil {
		log.Fatal(err)
	}
	fmt.Printf("Info: %+v", eetvInfo)

	recordings, err := eetvAPI.GetRecordings("", "", "")
	if err != nil {
		log.Fatal(err)
	}
	fmt.Printf("Recordings: %+v", recordings)
}
```