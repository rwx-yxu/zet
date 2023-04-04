# Better to manually parse JSON for custom error handling in Go
I am currently learning how to create REST APIs in Go and I am making use of the popular Gin
framework. Gin provides its own JSON unmarshal wrapper. Although this is convienient, I quickly
found that it was limiting in how I wanted to handle errors and make my own custom validations. This
is because Gin's ShouldBindJSON unmarshalling function automatically returns an error when it 
encounters an unknown field, but it doesn't give us the actual name of the unknown key. It is 
necessary to use json decoder with the disallowedfields flag set. Additionally, Gins
`ShouldBindJSON` cannot differentiate between a malformed JSON and string containing multiple JSON
values.
