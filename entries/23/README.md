# Golang : operator in slices and arrays

In go, deleting and element from an array or slice isn't as
straightforward as other languages like Java or Python that has easy
methods that will handle it for you.

Instead, the go idiom seems to be to use append to alter the underlying
array and create a new one using `:`.

What is `:`? `:` represents a lower and upper bound for a slice. Such
that is forms an inequality like low <= : < upper. The lower number is
inclusive and the upper is not. Where by the elements before and
including the lower indexes are excluded and the upper elements index is
not excluded.

For example:

```
func main() {
	s := []int{2, 3, 5, 7, 11, 13}

	s = s[2:]
	fmt.Println(s)
  //Output: 7,11,13
  //Index 2 is 5. For the lower number, 5 is included to be excluded.

  s = s[:2]
  fmt.Prinln(s)
  //Output:2,3,5
  //Index 2 is 5 but it is not inclsive to the exclusion.
  
  //Lower excludes elements from the start to the defined lower number.
  //Upper excludes elements after the index to the end of the slice.

}

```

This can used to remove an element from a slice by using the append
method to create two separate slices without the desired element to be
removed and join them.

```
func main(){
  //I want to remove 7
  s := []int{2, 3, 5, 7, 11, 13}
  //7 is index 3
  removeIndx := 3
  append(s[:removeIndx],s[removeIndx+1:]...)
  //s[:3] output is 2,3,5
  //s[3+1:]... output is 11,13
  //When combined with append method, you get 2,3,4,11,13 now without
  the 7.
}
```

The complexities for why this is the case can be read further in this
blog by the go team https://go.dev/blog/slices-intro



