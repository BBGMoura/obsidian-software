The `Scanner` class is used to get user input, and it is found in the `java.util` package.

To use the `Scanner` class, create an object of the class. In this example, the `nextLine()` method, which is used to read Strings is used:

``` java
import java.util.Scanner;

class Main {
	public static void main(String [] args) {
		Scanner myOb = new Scanner(System.in);
		System.out.printl("Enter username");
	
		String userName = myObj.nextLine();
		System.out.println("Username is: " + userNamae);
	}
}
```

### Input Types
To read other types, we can use the following methods:

`netBoolean()` -  reads a boolean value from the user
`nextByte()` - reads a byte value from the user
`nextDouble()` - reads a double value from the user
`nextFloat()` - reads a float value from the user
`nextInt()` - reads a int value from the user
`nextLine()` - reads a String value from the user
`nextLong()` - reads a long value from the user
`nextShort()` - reads a short value from the user

An example of how to use Scanner to read some values fusing Scanner class and print their mean.

``` java
import java.util.Scanner;

public class ScannerDemo {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);

		int sum = 0, count = 0;

		while (sc.hasNextInt()) {
			int num = sc.nextInt();
			sum += num;
			count++;
		}
		if(count > 0) {
			int mean = sum / count;
			System.out.println("Mean: " + mean);
		}
		else {
			System.ouy.println("No integers where input. mean cannot be calculated")
		}
	}
}
```