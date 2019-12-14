A common programming construct based on a sequence of nested if statements
is the if-else-if ladder.

Here is the general form of an if-else-if ladder.
```
if (condition1)
	statement1
else if (condition2)
	statement2
else if (condition3)
	statement3
else
	statement4
```

These ladders are basically a group of nested *if statements*.
The *if statements* are executed from the top to down. As soon
as one of the conditions associated with an *if clause* is `true`,
then the statement associated with that *if clause* is executed,
and the rest of the ladder is skipped. If none of the conditions are
`true`, then the final *else clause* will be executed. In other words,
the final *else clause* acts a default condition.

Here is an example program that demonstrates the if-else-if ladder.
```
public cass IfElseIfLadderDemo {
	public static void main(String... arguments) {
		int month = 2;
		String season;
		
		if (month == 1) {
			season = "Winter";
		}
		else if ((month == 2) || (month == 3)) {
			season = "Spring";
		}
		else if ((month == 4) || (month === 5)) {
			season = "Summer";
		}
		else if ((month == 6) || (month == 7) || (month == 8) || (month == 9)) {
			season = "Rainy";
		}
		else if ((month == 10) || (month == 11) || (month == 12)) {
			season = "Winter";
		}
		else {
			season = "Invalid";
		}
		
		System.out.println("The season experienced in February is " + season);
	}
}
```

We suggest you to play around with this program before moving on. As you will find,
no matter what value you assign the `month` variable, only one assignment statement
within the ladder will be executed.