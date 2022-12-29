# Golang Method has pointer receiver

This is my first time encountering a pointer error for Go. The error
appears when compiling which I got when trying to implement an interface
method on for one of my struct receivers.

The issue is how I had initialized the struct. I had initialized the
struct as: `player := Player{}` But the receiver is: `func (p
*Player)...` This is an issue because the initial declaration created a
`Player` struct which is different to what the receiver what expecting.
The receiver was expecting a pointer for player struct. The pointer was
necessary in this case because I was modifying underlying data of the
struct.

In order to avoid this, I had to change the initial declaration of the
struct to `player := &Player{}` for an address to the player which will
correspond to the pointer.
