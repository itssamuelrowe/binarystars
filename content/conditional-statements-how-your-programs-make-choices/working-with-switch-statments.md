The *switch statement* is a conditional statement that allows a value
to be tested for equality against a list of constants. Here, each constant
is called a *case*. Basically, the value being tested is compared with
each case.

The *switch statement* provides a better alternative to a large series
of if-else-if ladders.

Here is the general form of a *switch statement*.

```
switch (expression) {
	case constant1:
		// statements
		break;

	case constant2:
		// statements
		break;

	...

	case constant3:
		// statements
		break;

	default:
		// statements
}
```

The expression must produce an integer, string, character, or enumeration.
Each of the values specified in the *case clauses* must be compatible
with the expression.

Each *case* value must be a unique constant, not a variable. Duplicate *case*
values are not allowed.

The value of the expression is first evaluated. Then it is compared with
each of the constant values in the *case clauses*. If a match if found, the
code sequence under the *case clause* is executed.

If none of the constants match, then the *default clause* is executed.
However, the *default clause* is optional.

If no case matches and no default clause is present, then the switch statement
performs no action.

A break statement is used inside the switch statement to terminate a statement
sequence. When a break statement is encountered, the execution branches to the
first statement that follows the switch statement. In other words, the control goes
out of the switch statement.

If you don't write the break statement, control falls through to the next case clause
even if the case value does not match the value of the expression. Forgetting
to write break statements is one of the most common bugs.

Here is an example program.

```
public class WeekDay {

	public static void main(String... arguments) {
		String name;
		int day = 5;
		switch (day) {
			case 1:
				name = "Sunday";
				break;

			case 2:
				name = "Monday";
				break;

			case 3:
				name = "Tuesday";
				break;

			case 4:
				name = "Wednesday";
				break;

			case 5:
				name = "Thursday";
				break;

			case 6:
				name = "Friday";
				break;

			case 7:
				name = "Saturday";
				break;

			default:
				name = "Unknown";
		}

		System.out.println(name);
	}
}
```

Further, you can include more than one case value at a time.

Here's is an example of the seasons program using switch statement.

```
public class SwitchSeasonDemo {

	public static void main(String... arguments) {
		int month = 2;
		String season;

		switch (month) {
			case 1:
				season = "Winter";
				break;

			case 2:
			case 3:
				season = "Spring";
				break;

			case 4:
			case 5:
				season = "Summer";
				break;

			case 6:
			case 7:
			case 8:
			case 9:
				season = "Rainy";
				break;

			case 10:
			case 11:
			case 12:
				season = "Winter";
				break;

			default:
				season = "Invalid";
		}

		System.out.println("The season experienced in February is " + season);
	}
}
```

Further, you can nest switch statements just like if statements. This is called a
nested switch statement. In practice, nested switch statements are rare. But nevertheless,
you have it at your disposal.