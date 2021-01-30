# How to Remove Newline Characters from JSON Strings
## January 29, 2020

Take the json bytes and write it to a buffer using `json.Compact`.

```golang
// get the json bytes
jsonData := []byte(`{
	"foo": "string with spaces",
	"bar": 2,
}`)

// create a buffer
var buffer bytes.Buffer

// compact the stuffs
err = json.Compact(buffer, jsonData)
if err != nil {
	fmt.Println(err)
}

fmt.Println(buffer.String()) // {"foo":"string with spaces","bar":2}
```
