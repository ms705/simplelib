simplelib
=========

This project demonstrates how to create a Go (golang) package from a c++ class using [SWIG](http://www.swig.org/Doc3.0/Go.html) Read detailed instructions here: [http://zacg.github.io/blog/2013/06/06/calling-c-plus-plus-code-from-go-with-swig/](http://zacg.github.io/blog/2013/06/06/calling-c-plus-plus-code-from-go-with-swig/)


#### Details

#####Building

	cd simplelib
	make

#####Installing

	make install

#####Clean

	make cleanall

#####Running

```go
package main

import (
	"fmt"
	"github.com/zacg/simplelib"
	)

func main() {

	simpleClass := simplelib.NewSimpleClass()
	result := simpleClass.Hello()
	fmt.Println(result)

	strings := simplelib.NewStringVector()
	simpleClass.HelloString(strings)

	for i := 0; i < strings.Size(); i++ {
		fmt.Println(strings.Get(i))
	}

	bytes := simplelib.NewByteVector()
	simpleClass.HelloBytes(bytes)

	for i := 0; i < bytes.Size(); i++ {
		fmt.Printf("%s", string(bytes.Get(i)))
	}

}
```	
