## Generating worst cases for types based on operations on type interfaces:

### Everyone has seen at some point in their careeer:   
### "Oh no, you have experienced an out of bounds exception!"


- Number  
`+` : addition, given a types upperbound like uint8 = 2^8-1 and adding another 2^8-1 the new worstcase type is 2^9


## Grab interfaces off a type from a typed language:
"go" in this case: 

int8's interface:

https://stackoverflow.com/questions/24337145/get-name-of-struct-field-using-reflection
https://stackoverflow.com/questions/41694647/how-do-i-use-reflect-to-check-if-the-type-of-a-struct-field-is-interface
https://go.dev/ref/spec#LiteralType

here is the universe but we cant access it because it is not in the std lib
https://go.dev/src/go/types/universe.go

here is the std lib in go 
https://pkg.go.dev/std

another interesting file: 
https://github.com/golang/go/blob/28f4ea16a240af6c5a417e20be77745329f817f1/src/runtime/iface.go
