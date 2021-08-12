# golang-consuming-restapi
Simple example of consuming a RESTful API

<br>
The simplest example

```go
package main

import (
    "fmt"
    "io/ioutil"
    "log"
    "net/http"
    "os"
)

func main() {
    response, err := http.Get("http://pokeapi.co/api/v2/pokedex/kanto/")

    if err != nil {
        fmt.Print(err.Error())
        os.Exit(1)
    }

    responseData, err := ioutil.ReadAll(response.Body)
    if err != nil {
        log.Fatal(err)
    }
    
    fmt.Println(string(responseData))

}
```

<br><br>

[Example 1](https://tutorialedge.net/golang/consuming-restful-api-with-go/) <br>
[Example 2](https://levelup.gitconnected.com/consuming-a-rest-api-using-golang-b323602ba9d8)
