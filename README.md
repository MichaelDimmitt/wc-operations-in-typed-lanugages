## Generating worst cases for types based on operations on type interfaces:

"In typed languages you can basically write proofs so your programs always work. The programs can be logically sound." 
- can they though? 🤔 
- this repo aims to challenge that bold remark! 😅

### Everyone has seen at some point in their careeer:   
### "Oh no, you have experienced an out of bounds exception!"

- Number
```
Summary:
`+` : addition for uint8 type, we go out of bounds when:  
adding a number 2^8 to another number 2^8.  
Translated: 256+256 = 512, out of bounds! 2^9 is not a valid uint8.  

Think like a computer:  
`+` : addition, given 1-5 as an input where 1-5 is a range type and we keep doing addition.
worst case becomes 10  
worst case becomes 15  
worst case becomes 20  
... worst case for out of bounds is 256 + 2  
Give a worstcase warning that we may be out of bounds for an int8 after the 128th operation. Which is 2^8 / 2  

`+` : addition, given 1-5 as an input where 1-5 is a range type and we adding the number to itself.
worst case becomes 10 (5 * 2) (5 * 2^1)  
worst case becomes 20 (5 * 4) (5 * 2^2)  
worst case becomes 40 (5 * 8) (5 * 2^3)  
worst case becomes 80 (5 * 16) (5 * 2^4)  
... worst case becomes 5 * 2^n  
Give a worstcase warning that we may be out of bounds for an int8 after the 9th operation.
```

<!--
## Grab interfaces, operations, and functions off of types: ("go" in this case)

other phrases: "method set", "operations"
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
-->
