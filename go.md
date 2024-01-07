# Build
```bash
go build -o out_name source_file
```
# Http server

```go
package main
 
import (
    "net/http"
	"time"
	"fmt"
)
 
func main() {
    http.HandleFunc("/hello", func(w http.ResponseWriter, req *http.Request) {
		time.Sleep(10*time.Second)
		fmt.Println("Sleep Over.....") 
        w.Write([]byte("Hello World"))
    })
 
    http.ListenAndServe(":15000", nil)
}
```
