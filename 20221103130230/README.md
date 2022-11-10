# Use {} to define scope in Java switch case statements
Java requires {} after each case statement to define case scope.
Otherwise, variables that are defined in the case statement as local
scope.

```
//Incorrect variable day is considered a local variable without the {}
around case statements
		switch(dayNum) {
		case 1:
      String day = "Monday"
			break;
		case 2:
      String day = "Tuesday"
			break;
		default:
			String day = "Friday"
		}

//Correct. No error will be thrown since the variables in the case
statements are scoped to the case.
    switch(dayNum) {
		case 1:
		{
			String day = "Monday"
		}
			break;
		case 2:
		{
      String day = "Tuesday"
		}
			break;
		default:
			{
				String day = "Friday"
			}
		}
```

The scope is required when handling similar functionality for each case.
Such as marshalling data to different data types. The extra curly braces
does make the code less readable in my opinion if there is also a try catch as well.
This would be the same outcome with if statements as well.

Tags:

    #java #scope
