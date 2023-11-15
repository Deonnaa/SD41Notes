## [Week 2](https://github.com/SkillDistillery/SD41/blob/main/java1/README.md)

### Week 2 - Day 1

#### Packages
1. Namespaces
2. Introduction to Java Packages
3. Creating Packages
4. Package Names
5. Imports
6. Static Imports
7. Labs

```java
package com.skilldistillery.directorypath; //To minimize the chance of package name collisions.
```

```java
import com.skilldistillery.utilities.parsing.Parser; //To be able to use Parser.
import com.skilldistillery.utilities.parsing.*; //To be able to use all objects, does not use memory.

//main method
Parser parser = new Parser();
parser.parse();
```

`Lab 1 - ProductMain`
```java
package com.skilldistillery.packages.labs;

public class ProductMainStatics {

  Product product;

  public static void main(String[] args) {
    ProductMainStatics app = new ProductMainStatics();
    app.go();
  }

  public ProductMainStatics() {
    product = new Product();
  }

  public void go() {
    utilMethod();
    helperMethod();
  }
}
```

#### String and StringBuilder
1. The String Class
2. The String Pool
3. String Methods
4. The StringBuilder Class
5. StringBuilder Methods
6. Writing toString() Methods
7. Labs

`StringAndStringBuilder/com.skilldistillery.stringstringbuilder.drills.StringPoolTesting`
```java
class OtherClass {
	public static String coding = "AlwaysCoding";
}

public class StringPoolTesting {
	private String coding = "Always" + "Coding";

	public static void main(String[] args) {
		StringPoolTesting tester = new StringPoolTesting();
		tester.test();
	}

	private void test() {
		String coding = "AlwaysCoding";
		String coding2 = new String("AlwaysCoding");
		String always = "Always";

//     true or false: false
		System.out.println(coding == coding2);
//     true or false: true
		System.out.println(coding == this.coding);
//     true or false: true
		System.out.println(coding == OtherClass.coding);
//     true or false: true
		System.out.println(coding == "AlwaysCoding");
//     true or false: true
		System.out.println(coding == "Always" + "Coding");
//     true or false: flase
		System.out.println(coding == always + "Coding");
//     true or false: true
		System.out.println(coding == "Al" + "waysCoding");
//     true or false:true
		System.out.println(coding == (always + "Coding").intern());
	}
}
```

`StringAndStringBuilder/src/com.skilldistillery.stringstringbuilder.drills.SSNMasker`
```java
public class SSNMasker {

	/**
	 * Returns an SSN (Social Security Number) string with the first five digits
	 * replaced with 'X'.
	 * 
	 * @param ssn An SSN sting in the format 123-45-6789
	 * @return A masked SSN string in the format XXX-XX-6789
	 */
	public String maskSSN(String ssn) {
		String maskedSSN = null;

		// CODE HERE
		// use substring and concatenation to return a masked SSN.
		String lastFour = ssn.substring(7, 11);
		maskedSSN = "XXX-XX-" + lastFour;
		return maskedSSN;
	}
}
```

`StringAndStringBuilder/test/com.skilldistillery.stringstringbuilder.drills.SSNMaskerTests`
```java
public class SSNMaskerTests {
  SSNMasker masker;

	@Before
	public void setUp() throws Exception {
		masker = new SSNMasker();
	}

	@After
	public void tearDown() throws Exception {
		masker = null;
	}

	@Test
	public void test_maskSSN_returns_ssn_with_first_five_digits_masked_with_X() {
		String ssn = "123-45-6789";
		String masked = masker.maskSSN(ssn);
		String expected = "XXX-XX-6789";
		assertEquals(expected, masked);
		ssn = "666-55-4321";
		masked = masker.maskSSN(ssn);
		expected = "XXX-XX-4321";
	}

}
```

`StringAndStringBuilder/com.skilldistillery.stringstringbuilder.drills.UserCommentDriver`
```java
public class UserCommentDriver {

	public static void main(String[] args) {
		UserCommentDriver driver = new UserCommentDriver();
		driver.go();
	}

	private void go() {
		UserComment comment1 = new UserComment(42, null, "2018-01-04", "14:59:23", "bdobbs", "I love coding in Java!");

		UserComment comment2 = new UserComment(47, comment1, "2018-01-04", "15:03:12", "jsmith", "Me too!");

		System.out.println(comment1);
		System.out.println(comment2);

	}
}
```
```java
//UserComment.java

@Override
	public String toString() {
		return "UserComment [commentId=" + commentId + ", inReplyToComment=" + inReplyToComment + ", date=" + date
				+ ", time=" + time + ", userName=" + userName + ", commentText=" + commentText + "]";
	}
```

`Lab 1 - StringLab.java`
```java
public class StringLab {

	public static void main(String[] args) {
		StringLab lab = new StringLab();
		lab.go();
	}

	private void go() {
		// Using String methods, determine and print whether 'testString':
		// 1. Starts with 'abc'
		// 2. Ends with 'ld!'
		// 3. Contains 'wor'
		String testString = "Hello world!";

		System.out.println(testString.startsWith("abc"));
		System.out.println(testString.endsWith("ld!"));
		System.out.println(testString.contains("wor"));

		// Using String methods, print the following information
		// about 'testString2':
		// 1. The character at index 3
		// 2. The number of characters in the String
		// 3. The contents of the String in all uppercase
		// 4. The contents of the String without white space on either side

		String testString2 = "   Hello Java Coding World!   ";

		System.out.println(testString2.charAt(3));
		System.out.println(testString2.length());
		System.out.println(testString2.toUpperCase());
		System.out.println(testString2.trim());
	}
}
```

`Lab 2 - StringBuilderLab.java`
```java
public class StringBuilderLab {

	public static void main(String[] args) {
		StringBuilderLab lab = new StringBuilderLab();
		lab.go();
	}

	private void go() {
		String original = "Java world.";

		StringBuilder sb = new StringBuilder(original);
		System.out.println(sb);

		// Use only StringBuilder methods on sb to change the text to:
		// Hello, Java coding world! Always Be Coding!
		// Print out sb after each step.

		sb.setCharAt(sb.length() - 1, '!');
		System.out.println(sb);

		sb.insert(5, "coding ");
		System.out.println(sb);

		sb.insert(0, "Hello, ");
		System.out.println(sb);

		sb.append(" Always Be Coding!");
		System.out.println(sb);

		String result = sb.toString();
		System.out.println(result);
	}
}
```

`Lab 3 - UserComment.java`
```java
@Override
  public String toString() {
    String result = "On " + date + " at " + time + ", " + userName + " posted this comment: ["
                    + commentText + "]";
    return result;
  }
```

`Lab 4 - UserComment2.java`
```java
@Override
  public String toString() {
    StringBuilder sb = new StringBuilder("On ");
    sb.append(date)
      .append(" at ")
      .append(time)
      .append(", ")
      .append(userName)
      .append(" posted this comment: [")
      .append(commentText)
      .append("]");
    return sb.toString();
  }
```

`Lab 5 - UserComment3.java`
```java
@Override
  public String toString() {
    StringBuilder builder = new StringBuilder();
    builder.append("UserComment3 [commentId=").append(commentId).append(", ");
    if (inReplyToComment != null)
      builder.append("inReplyToComment=").append(inReplyToComment).append(", ");
    if (date != null)
      builder.append("date=").append(date).append(", ");
    if (time != null)
      builder.append("time=").append(time).append(", ");
    if (userName != null)
      builder.append("userName=").append(userName).append(", ");
    if (commentText != null)
      builder.append("commentText=").append(commentText);
    builder.append("]");
    return builder.toString();
  }
```

#### Project: Mad Libs

### Week 2 - Day 2

#### ASCII and Unicode Data
1. Standards
2. ASCII
3. Unicode
4. Labs

`ASCIIData/com.skilldistillery.characters.drills.ASCIICharacters`
```java
public class ASCIICharacters {

	public static void main(String[] args) {
		// In a for loop, iterate through the number 0 to 127,
		// printing each number and the char representation
		// of that number (by casting it to a char) on a separate line.
		for (int i = 0; i < 128; i++) {
			char ASCIIi = (char) i;
			System.out.println("Numeral Value:" + i + " ASCII Value:" + ASCIIi);
		}
	}
}
```

`ASCIIData/com.skilldistillery.characters.drills.UnicodeOutput`
```java
public class UnicodeOutput {

	public static void main(String[] args) {
		// Write the characters
		// '\u261d', '\u270a', '\u270b', '\u270c'
		// to the screen.
		System.out.println('\u261d' + "" + '\u270a' + "" + '\u270b' + "" + '\u270c');
	}
}
```

`ASCIIData/com.skilldistillery.characters.drills.SuppChars`
```java
public class SuppChars {

	public static void main(String[] args) {
		// Write the String "\uD83C\uDCA1" to the screen.
		System.out.println("\uD83C\uDCA1");

		// Add the statement System.out.println(Character.toChars(0x1f0a1));
		System.out.println(Character.toChars(0x1f0a1));

		// Use Character.toChars() to output the code points 0x1F600 through 0x1F64F
		// Add a newline every 16 characters.
		int counter = 0;
		for (int i = 0x1F600; i <= 0x1F64F; i++) {
			System.out.print(Character.toChars(i));
			counter++;
			if (counter % 16 == 0) {
				System.out.println();
				counter = 0;
			}
		}
	}
}
```

`Lab 1 - AlphaNumCheck.java`
```java
public class AlphaNumCheck {

	public static void main(String[] args) {
		run();
	}

	public static void run() {
		Scanner sc = new Scanner(System.in);

		// Make an instance of this class
		AlphaNumCheck anc = new AlphaNumCheck();

		System.out.print("Enter a word or sentence: ");
		String input = anc.getSentence(sc);

		boolean result = anc.checkAlphaSentence(input);

		if (result) {
			System.out.println("The sentence contains only letters.");
		} else {
			System.out.println("The sentence contains non-letters.");
		}
		sc.close();
	}

	public String getSentence(Scanner sc) {
		return sc.nextLine();
	}

	public boolean checkAlphaSentence(String input) {
		char[] chars = input.toCharArray();
		boolean result = true;
		for (int i = 0; i < chars.length; i++) {
			char c = chars[i];
			if (c >= 65 && c <= 90 || c >= 'a' && c <= 'z') {
				continue;
			}
			result = false;
			break;
		}
		return result;
	}
}
```

`Lab 2 - AlphaNumCheck.java`
```java
public boolean checkAlphaNumSpaceSentence(String input) {
    char[] chars = input.toCharArray();
    boolean result = true;
    for (int i = 0; i < chars.length; i++) {
      char c = chars[i];
      if(c >= 65 && c <= 90 
          || c >= 'a' && c <= 'z'
          || c == 32
          || c >= '0' && c <= '9') {
        continue;
      }
      result = false;
      break;
    }
    
    return result;
  }
```

#### Objects and Classes
1. Classes and Objects
2. Constructors
3. The Default Constructor
4. Objects in Memory
5. Imagining the Heap
6. Visibility

`Objects/com.skilldistillery.objs.drills.Dog`
```java
public class Dog {
	public String breed;
	public String name;
	public int weight;

	// Add a constructor with parameters to initialize breed and weight.
	public Dog(String breedDog, int weightDog) {
		breed = breedDog;
		weight = weightDog;
	}

	// Add a constructor with parameters to initialize name, breed, and weight.
	public Dog(String name, String someBreed, int howManyLbs) {
		this.name = name;
		breed = someBreed;
		weight = howManyLbs;
	}

	public void displayDogInfo() {
		System.out.println("Dog [breed=" + breed + ", name=" + name + ", weight=" + weight + "]");
	}

	public static void main(String[] args) {
		// Create three dog instances and call the displayDogInfo method on each Dog
		// object.
		Dog newDog = new Dog("Poodle", 30);
		newDog.displayDogInfo();

		Dog myDog = new Dog("Pit Mix", 60);
		myDog.displayDogInfo();

		Dog yourDog = new Dog("Lab", 100);
		yourDog.displayDogInfo();

		Dog fredsDog = new Dog("Spot", "mutt", 10);
		fredsDog.displayDogInfo();
	}
}
```

`Objects/com.skilldistillery.objs.drills.BankApp`
```java
public class BankApp {

	public static void main(String[] args) {
		BankApp b = new BankApp();
		b.run();
	}

	void run() {
		Account acc1 = new Account("ACC-10001", 305.32);
		Account acc2 = new Account("ACC-10002", 9053.23);

		printAccountData(acc1);
		printAccountData(acc2);
//    	acc1.setBalance(305.32 + 100);
	}

	void printAccountData(Account account) {
		System.out.println(account.getAccountId() + " balance: " + account.getBalance());
	}
}
//cmd + opt + s
//generate getters and setters
```

#### Drawing Objects and Their Relationships
1. Representing Objects with Diagrams
2. UML Class Diagram
3. Classes and Their Associations
4. Labs

#### Introduction to JUnit
1. Testing Java Applications
2. Building and Deploying Software
3. JUnit
4. Test Classes
5. Writing @Test Methods
6. assert Methods
7. @Before and @After
8. Test-Driven Development (TDD)
9. Labs

#### Project: Caesar Cipher

### Week 2 - Day 3

#### Encapsulation
1. Changing Instance Fields
2. Visibility and Access Modifiers
3. Encapsulation
4. Getters and Setters
5. The this Keyword
6. Labs

`Encapsulation/com.skilldistillery.encapsulation.drills.BankApp`
```java
public class BankApp {

  public static void main(String[] args) {
    BankApp b = new BankApp();
    b.run();
  }
  
  void run(){
    Account acc1 = new Account("ACC-10001", 305.32);
    Account acc2 = new Account("ACC-10002", 9053.23);
    
    printAccountData(acc1);
    printAccountData(acc2); 
  }
  
  void printAccountData(Account account) {
    System.out.println(account.accountId + " balance: " + account.balance); //Can't access private data (accountId, balance)
  }
}
```

`Encapsulation/com.skilldistillery.encapsulation.drills.Account`
```java
	private double balance;
	private String accountId;

	public Account(String aId) {
		accountId = aId;
	}

	public Account(String aId, double initialBalance) {
		balance = initialBalance;
		accountId = aId;
	}

	public void deposit(double amount) {
		balance = balance + amount;
	}

	public void withdraw(double amount) {
		balance = balance - amount;
	}
}
```

`Encapsulation/com.skilldistillery.encapsulation.drills.BankApp`
```java
public class BankApp {

	public static void main(String[] args) {
		BankApp b = new BankApp();
		b.run();
	}

	void run() {
		Account acc1 = new Account("ACC-10001", 305.32);
		Account acc2 = new Account("ACC-10002", 9053.23);

		printAccountData(acc1);
		printAccountData(acc2);
	}

	void printAccountData(Account account) {
		System.out.println(account.getAccountId() + " balance: " + account.getBalance());
	}
}
```

`Encapsulation/com.skilldistillery.encapsulation.drills.Account`
```java
public class Account {
	  private double balance;
	  private String accountId;

	  public Account(String aId) {
	    accountId = aId;
	  }

	  public Account(String aId, double initialBalance) {
	    balance = initialBalance;
	    accountId = aId;
	  }
	  
	  // "getter" and "setter" methods
	  public double getBalance() {
	    return balance;
	  }

	  public void setBalance(double bal) {
	    balance = bal;
	  }

	  public String getAccountId() {
	    return accountId;
	  }

	  public void setAccountId(String id) {
	    accountId = id;
	  }

	  public void deposit(double amount) {
	    balance = balance + amount;
	  }

	  public void withdraw(double amount) {
	    balance = balance - amount;
	  }
	}
```

`Encapsulation/com.skilldistillery.encapsulation.drills.Student`
```java
public class Student {

	private int[] scores;
	private double average;

	public int[] getScores() {
		return scores;
	}

	public double getAverage() {
		return average;
	}

	private void computeAverage() {
		// valid code to compute average
		// average = update average value
		if (scores != null && scores.length > 0) {
			int sum = 0;
			for (int score : scores) {
				sum += score;
			}
			average = (double) sum / scores.length;
		} else {
			average = 0; // Handle the case when there are no scores.
		}
	}

	public Student() {
		computeAverage();
	}
}
```

`Encapsulation/com.skilldistillery.encapsulation.drills.Account`
```java
public class Account {
	private double balance;
	private String accountId;

	public Account(String aId) {
		accountId = aId;
	}

	public Account(String aId, double initialBalance) {
		balance = initialBalance;
		accountId = aId;
	}

	// "getter" and "setter" methods
	public double getBalance() {
		return balance;
	}

	public void setBalance(double bal) {
		this.balance = balance;
	}

	public String getAccountId() {
		return accountId;
	}

	public void setAccountId(String id) {
		this.accountId = accountId;
	}

	public void deposit(double amount) {
		balance = balance + amount;
	}

	public void withdraw(double amount) {
		balance = balance - amount;
	}
}
```

`Lab 1 - Car.java`
```java
public class Car {
	private String make;
	private String model;
	private String color;
	private int numberOfWheels;
	private double purchasePrice;


	public Car() {
		
	}

	public Car(String make1, String model1, String color1, int wheels, double price) {
		this.make = make1;
		this.model = model1;
		this.color = color1;
		this.numberOfWheels = wheels;
		this.purchasePrice = price;
	}

	public Car(String make1, String model1, String color1, int wheels) {
		this.make = make1;
		this.model = model1;
		this.color = color1;
		this.numberOfWheels = wheels;
	}

	public String getMake() {
		return make;
	}

	public void setMake(String make) {
		this.make = make;
	}

	public String getModel() {
		return model;
	}

	public void setModel(String model) {
		this.model = model;
	}

	public String getColor() {
		return color;
	}

	public void setColor(String color) {
		this.color = color;
	}

	public int getNumberOfWheels() {
		return numberOfWheels;
	}

	public void setNumberOfWheels(int numberOfWheels) {
		this.numberOfWheels = numberOfWheels;
	}

	public double getPurchasePrice() {
		return purchasePrice;
	}

	public void setPurchasePrice(double purchasePrice) {
		this.purchasePrice = purchasePrice;
	}

	public void displayCar() {
		String carData = toString();
		System.out.println(carData);
	}

	public String toString() {
		String output = "make= " + make + ", model= " + model + ", color= " + color + ", numberOfWheels= "
				+ numberOfWheels + ", purchasePrice= " + purchasePrice;
		return output;
	}
}
```

`Lab 1 - CarTester.java`
```java
public class CarTester {

	public static void main(String[] args) {
		// Create two Cars and assign fields
		Car car1 = new Car("Dodge", "Stratus", "Blue", 4, 15412);
		Car car2 = new Car("Ford", "F-950", "Neon", 10, 70000);
		Car car3 = new Car();

		// Have the cars display themselves
		car1.displayCar();
		car2.displayCar();
		car3.displayCar();

		String car1Data = car1.toString();
		String car2Data = car2.toString();
		String car3Data = car3.toString();

		// Get the cars' data and display that
		System.out.println("Car 1 data: " + car1Data);
		System.out.println("Car 2 data: " + car2Data);
		System.out.println("Car 3 data: " + car3Data);
	}
}
```

`Lab 2 - ParkingLot.java`
```java
public class ParkingLot {
	private int numCars;
	private Car[] cars;
	private int MAX_CARS = 10;

	public ParkingLot() {
		cars = new Car[MAX_CARS];
	}

	public void addCar(Car aCar) {
		if (numCars == MAX_CARS) {
			System.out.println("SOL! Good luck making your flight!");
		} else {
			for (int i = 0; i < cars.length; i++) {
				if (cars[i] == null) {
					cars[i] = aCar;
					numCars++;
					break;
				}
			}
		}
	}

	public Car[] getCars() {
		Car[] allParkedCars = new Car[numCars];
		for (int i = 0; i < cars.length; i++) {
			if (cars[i] != null) {
				allParkedCars[i] = cars[i];
			}
		}
		return allParkedCars;
	}
}
```

`Lab 2 - ParkingLotTester.java`
```java
public class ParkingLotTester {

	public static void main(String[] args) {
		ParkingLotTester crt = new ParkingLotTester();
		crt.run();
	}

	private void run() {
		ParkingLot cr = new ParkingLot();

		Car[] cars = cr.getCars();

		System.out.println("Number of initial cars: " + cars.length);

		Car car1 = new Car("Black", "Dodge", "Stratus", 4, 15412.0);

		Car car2 = new Car();
		car2.setColor("Neon");
		car2.setMake("Ford");
		car2.setModel("F950");
		car2.setNumberOfWheels(10);
		car2.setPurchasePrice(74999.0);

		cr.addCar(car1);
		cr.addCar(car2);

		// Get the car array
		cars = cr.getCars();

		// Print it
		printCars(cars);

		System.out.println("Total cars returned: " + cars.length);
	}

	private void printCars(Car[] cars) {
		for (Car car : cars) {
			car.displayCar();
		}
	}
}
```

#### Object Initialization
1. this vs. this()
2. Initializing Static Fields
3. Initializing Instance Fields
4. Order of Initialization
5. Constant Fields and Variables
6. private Methods
7. Labs
```java
public class Car2 {
  private String make, model, color;
  private int numberOfWheels;
  private double purchasePrice;

  public Car2(String make, String model, String color, int numberOfWheels) {
    this(make, model, color, numberOfWheels, 0.0);
  }

  public Car2(String make, String model, String color, int numberOfWheels, double purchasePrice) {
    this.make = make;
    this.model = model;
    this.color = color;
    this.numberOfWheels = numberOfWheels;
    this.purchasePrice = purchasePrice;
  }
  //...
}
```

#### Inheritance in Java
1. Inheritance
2. The extends Keyword
3. final Classes *
4. UML and extends
5. Inheriting Fields *
6. Inheriting Methods *
7. Lab - Creating a Class Hierarchy

`Inheritance/com.skilldistillery.inheritance.drills.Employee`
```java
public class Employee extends Person {

	private String title;
	private double Salary;
}
```

`Inheritance/com.skilldistillery.inheritance.drills`
```java
public class TestClass extends Object{

}
//Try to make TestClass extend System by adding extends System.
//Try to make TestClass extend String.
//Try to make TestClass extend StringBuilder.
//Try to make TestClass extend Integer.
//It didn't work. Make TestClass extend Object.
```

`Inheritance/com.skilldistillery.inheritance.drills.Employee`
```java
public class Employee extends Person {

	private String title;
	private double Salary;

	// Add a no-arg constructor to Employee.
	public Employee() {
	
	}

	// Add a constructor to Employee with parameters for firstName, lastName, age,
	// title, and salary.
	// Set the fields firstName, lastName, and age the same way as title and salary
	// - using the . operator.
	public Employee(String firstName, String lastName, int age, String title, double Salary) {
		this.firstName = firstName;
		this.lastName = lastName;
		this.age = age;
		this.title = title;
		this.Salary = Salary;
	}

	// Add a method to Employee called public String getInfo()
	// Return a String containing the object's information in the format firstName
	// lastName age title salary.
	public String getInfo() {
		return firstName + " " + lastName + " " + age + " " + title + " " + salary;
	}
}
```

`Inheritance/com.skilldistillery.inheritance.drills.EmployeeApp`
```java
public class EmployeeApp {

	public static void main(String[] args) {
		EmployeeApp app = new EmployeeApp();
		app.run();
	}

	private void run() {
		Person pers = null;
		// Create a Person object and assign it to pers. Give the person a firstName,
		// lastName, and age using either the constructor or setters.
		pers = new Person();
		pers.setFirstName("Anthony");
		pers.setLastName("King");
		pers.setAge(31);

		// Call getInfo() and print the Person's information to the screen.
		System.out.println(pers.getInfo());

		Employee emp2 = null;

		// Create an Employee object using the five-argument constructor, and
		// assign it to emp2.
		emp2 = new Employee("Dee", "G", 25, "Instructor", 100); // creating new object using ctor from Employee class

		// Call getInfo() and print the Employee's information to the screen.
		System.out.println(emp2.getInfo());
	}
}
```

`Inheritance/com.skilldistillery.inheritance.drills.Employee`
```java
public String getInfo() {
		return getName() + " " + age + " " + title + " " + Salary;
	}
```

`Lab 1 - Vehicle.java`
```java
public class Vehicle {

	protected double purchasePrice;

	public Vehicle() {
	}

	public Vehicle(double purchasePrice) {
		this.purchasePrice = purchasePrice;
	}

	public double getPurchasePrice() {
		return purchasePrice;
	}

	public void setPurchasePrice(double purchasePrice) {
		this.purchasePrice = purchasePrice;
	}

	@Override
	public String toString() {
		return "Vehicle [purchasePrice=" + purchasePrice + "]";
	}
}
```

`Lab 2 - Automobile.java`
```java
public class Automobile extends Vehicle {

	private String make;
	private String model;
	private int year;
	private int numberOfWheels;
	private double speedInMph;

	public Automobile() {
	}

	public Automobile(String make, String model, int year, int numberOfWheels, double speedInMph,
			double purchasePrice) {
		super(purchasePrice);
		this.make = make;
		this.model = model;
		this.year = year;
		this.numberOfWheels = numberOfWheels;
		this.speedInMph = speedInMph;
		this.purchasePrice = purchasePrice;
	}
	
	public String getMake() {
		return make;
	}

	public void setMake(String make) {
		this.make = make;
	}

	public String getModel() {
		return model;
	}

	public void setModel(String model) {
		this.model = model;
	}

	public int getYear() {
		return year;
	}

	public void setYear(int year) {
		this.year = year;
	}

	public int getNumberOfWheels() {
		return numberOfWheels;
	}

	public void setNumberOfWheels(int numberOfWheels) {
		this.numberOfWheels = numberOfWheels;
	}

	public double getSpeedInMph() {
		return speedInMph;
	}

	public void setSpeedInMph(double speedInMph) {
		this.speedInMph = speedInMph;
	}

	@Override
	public String toString() {
		return "Automobile [make=" + make + ", model=" + model + ", year=" + year + ", numberOfWheels=" + numberOfWheels
				+ ", speedInMph=" + speedInMph + ", purchasePrice=" + purchasePrice + "]";
	}
}
```

`Lab 3 - Boat.java`
```java
public class Boat extends Vehicle {

	protected String name;
	protected double speedInKnots;
	protected int lengthInFeet;

	public Boat() {

	}

	public Boat(String name, double speedInKnots, int lengthInFeet, double purchasePrice) {
		this.name = name;
		this.speedInKnots = speedInKnots;
		this.lengthInFeet = lengthInFeet;
		this.purchasePrice = purchasePrice;
	}

	@Override
	public String toString() {
		return "Boat [name=" + name + ", speedInKnots=" + speedInKnots + ", lengthInFeet=" + lengthInFeet
				+ ", purchasePrice=" + purchasePrice + "]";
	}
}
```

`Lab 4 - Truck.java`
```java
public class Truck extends Automobile {
	protected int bedSizeInCubicFeet;

	public Truck() {

	}

	public Truck(double purchasePrice, String make, String model, int year, int numberOfWheels, double speedInMph,
			int bedSizeInCubicFeet) {
		this.purchasePrice = purchasePrice; // Vehicle field
		this.make = make; // Automobile fields
		this.model = model;
		this.year = year;
		this.numberOfWheels = numberOfWheels;
		this.speedInMph = speedInMph;
		this.bedSizeInCubicFeet = bedSizeInCubicFeet;
	}
}
```

`Lab 5 - VehicleTestApp.java`
```java
public class VehicleTestApp {

	public static void main(String[] args) {
		Automobile sc = new Automobile();
		System.out.println(sc.toString());

		Boat bobber = new Boat();
		System.out.println(bobber.toString());

		Truck coalRoller = new Truck();
		System.out.println(coalRoller.toString());

	}
}
```

#### Visibility
1. Field and Method Visibility
2. Getters and Setters
3. Lab - Improving Encapsulation

#### Project: Food Trucks

### Week 2 - Day 4

#### Superclasses
1. Using a Superclass's Methods and Fields
2. Constructors and Inheritance
3. Rules for super()
4. The Object Class
5. Labs

`SuperClasses/com.skilldistillery.inheritance.drills.Employee`
```java
public class Employee extends Person {
  private String title;
  private double salary;

  public Employee() {
  }

  public Employee(String firstName, String lastName, int age,
      String title, double salary) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
    this.title = title;
    this.salary = salary;
  }
  
  // Call the parent method
  public String getInfo() {
    return super.getInfo() + " " + title + " " + salary;
  }

  public String getTitle() {
    return title;
  }

  public void setTitle(String title) {
    this.title = title;
}

public double getSalary() {
	return salary;
}

public void setSalary(double salary) {
	this.salary = salary;
}
}
```

`SuperClasses/com.skilldistillery.inheritance.drills.DataAnalyst`
```java
import com.skilldistillery.superclasses.drills.Employee;

public class DataAnalyst extends Employee {
  private String securityClearance;
  
  public DataAnalyst(String securityClearance, String firstName, String lastName, int age, String title, double salary) {
    this.setSecurityClearance(securityClearance);
    this.setFirstName(firstName);
    this.setLastName(lastName);
    this.setAge(age);
	this.setTitle(title);
	this.setSalary(salary);
}

public String getSecurityClearance() {
	return securityClearance;
}

public void setSecurityClearance(String securityClearance) {
	this.securityClearance = securityClearance;
}

// Call the parent method
public String getInfo() {
	return super.getInfo() + " " + securityClearance;
}
}
```

`SuperClasses/com.skilldistillery.inheritance.drills.EmployeeApp`
```java
import com.skilldistillery.superclasses.drills.Person;

public class EmployeeApp {

	public static void main(String[] args) {
		EmployeeApp app = new EmployeeApp();
		app.run();
	}

	private void run() {
		Person pers = null;
		pers = new Person("Ronnie", "Dobbs", 34);
		System.out.println(pers.getInfo());

		Employee6 emp = null;
		emp = new Employee6("Bob", "Dobbs", 55, "VP of Sales", 138_000.00);
		System.out.println(emp.getInfo());

		DataAnalyst dataAnalyst = new DataAnalyst("TOP SECRET", "James", "Java", 45, "Analyst IV", 120_000.00);
		System.out.println(dataAnalyst.getInfo());
	}
}
```

`Lab 1 - Vehicle.java`
```java
public class Vehicle {

	private double purchasePrice;

	public Vehicle(double purchasePrice) {
		this.purchasePrice = purchasePrice;
	}

	public double getPurchasePrice() {
		return purchasePrice;
	}

	public void setPurchasePrice(double purchasePrice) {
		this.purchasePrice = purchasePrice;
	}

	public String toString() {
		return "Vehicle [purchasePrice=" + purchasePrice + "]";
	}
}
```

`Lab 1 - Automobile.java`
```java
import com.skilldistillery.superclasses.labs.vehicles.Vehicle;

public class Automobile extends Vehicle {
	private String make;
	private String model;
	private int year;
	private int numberOfWheels;
	private double speedInMph;

	public Automobile(double purchasePrice, String make, String model, int year, int numberOfWheels,
			double speedInMph) {
		super(purchasePrice);
		this.make = make;
		this.model = model;
		this.year = year;
		this.numberOfWheels = numberOfWheels;
		this.speedInMph = speedInMph;
	}

	public String toString() {
		return "Automobile [purchasePrice=" + getPurchasePrice() + ", make=" + make + ", model=" + model + ", year="
				+ year + ", numberOfWheels=" + numberOfWheels + ", speedInMph=" + speedInMph + "]";
	}

	public String getMake() {
		return make;
	}

	public void setMake(String make) {
		this.make = make;
	}

	public String getModel() {
		return model;
	}

	public void setModel(String model) {
		this.model = model;
	}

	public int getYear() {
		return year;
	}

	public void setYear(int year) {
		this.year = year;
	}

	public int getNumberOfWheels() {
		return numberOfWheels;
	}

	public void setNumberOfWheels(int numberOfWheels) {
		this.numberOfWheels = numberOfWheels;
	}

	public double getSpeedInMph() {
		return speedInMph;
	}

	public void setSpeedInMph(double speedInMph) {
		this.speedInMph = speedInMph;
	}
}
```

`Lab 1 - Truck.java`
```java
import com.skilldistillery.superclasses.labs.vehicles.Automobile;

public class Truck extends Automobile {
	protected int bedSizeInCubicFeet;

	public Truck(double purchasePrice, String make, String model, int year, int numberOfWheels, double speedInMph,
			int bedSizeInCubicFeet) {
		super(purchasePrice, make, model, year, numberOfWheels, speedInMph);
		this.bedSizeInCubicFeet = bedSizeInCubicFeet;
	}

	public int getBedSizeInCubicFeet() {
		return bedSizeInCubicFeet;
	}

	public void setBedSizeInCubicFeet(int bedSizeInCubicFeet) {
		this.bedSizeInCubicFeet = bedSizeInCubicFeet;
	}
}
```

`Lab 1 - Boat.java`
```java
import com.skilldistillery.superclasses.labs.vehicles.Vehicle;

public class Boat extends Vehicle {
	protected String name;
	protected double speedInKnots;
	protected int lengthInFeet;

	public Boat(double purchasePrice, String name, double speedInKnots, int lengthInFeet) {
		super(purchasePrice);
		this.name = name;
		this.speedInKnots = speedInKnots;
		this.lengthInFeet = lengthInFeet;
	}

	public String toString() {
		return "Boat [purchasePrice=" + getPurchasePrice() + ", name=" + name + ", speedInKnots=" + speedInKnots
				+ ", lengthInFeet=" + lengthInFeet + "]";
	}
}
```

`Lab 1 - VehicleTestApp`
```java
public class VehicleTestApp {

	public static void main(String[] args) {
		Automobile a = new Automobile3(90000.00, "Dundreary", "Stretch", 2008, 4, 105);
		Boat b = new Boat3(145000.00, "Reefer", 21, 25);
		Truck t = new Truck3(22_000, "Vapid", "Bobcat", 2006, 4, 88, 55);

		System.out.println(a.toString());
		System.out.println(b.toString());
		System.out.println(t.toString());
	}
}
```

#### Polymorphism and Overriding
1. Polymorphism in Java
2. Overriding Superclass Behavior
3. @Override
4. Rules for Overriding
5. Lab - Using Polymorphism

#### Abstract Classes
1. Abstract Classes
2. Abstract Methods
3. Using Abstract Classes
4. Labs

#### Polymorphism and Casting
1. Casting
2. Downcasting
3. Casting and Precedence
4. Hiding Instance Fields
5. Labs

#### Project: Animal Sanctuary

### Week 2 - Day 5

#### Equals and Hashcode
1. Comparing References
2. Object.equals()
3. Defining an equals() Method
4. Determining Equality
5. hashCode()
6. Labs

#### The Primitive-Type Wrapper Classes
1. Wrapper Classes
2. Important Wrapper Class Methods
3. Comparing Wrapper Objects
4. Autoboxing
5. Float and Double
6. Integer-type Wrappers
7. Character
8. Boolean
9. Labs

`WrapperClasses/com.skilldistillery.wrapperclasses.drills.ParseDrill`
```java
public class ParseDrill {

	public static void main(String[] args) {
		ParseDrill drill = new ParseDrill();
		drill.go();
	}

	private void go() {
		// Write statements to determine which strings can be parsed,
		// and if so print the result, when parsed to:

		// Example:
		System.out.println(Integer.parseInt("42")); // No problem, 42

		// int:
		// "1000000000"
		System.out.println(Integer.parseInt("1000000000")); // No problem, 1000000000
		// "-1000000000"
		System.out.println(Integer.parseInt("-1000000000")); // No problem, -1000000000
		// "+1000000000"
		System.out.println(Integer.parseInt("+1000000000")); // No problem, 1000000000
		// " 1000000000 "
//    System.out.println(Integer.parseInt("  1000000000   ")); // NumberFormatException
		// "0x123abc"
//    System.out.println(Integer.parseInt("0x123abc")); // NumberFormatException
		// Note that a hexadecimal (or other base integer) can be parsed by passing
		// a radix to the overloaded Integer.parseInt; omit the "0x" prefix.
		System.out.println(Integer.parseInt("123abc", 16)); // NumberFormatException
		// "1.0"
//    System.out.println(Integer.parseInt("1.0")); // NumberFormatException
		// "1,000,000,000"
//  System.out.println(Integer.parseInt("1,000,000,000")); // NumberFormatException
		// "1_000_000_000"
//  System.out.println(Integer.parseInt("1_000_000_000")); // NumberFormatException
		// "10000000000"
//  System.out.println(Integer.parseInt("10000000000")); // NumberFormatException
		// ""
//  System.out.println(Integer.parseInt("")); // NumberFormatException
		// null
//  System.out.println(Integer.parseInt(null)); // NumberFormatException

		// long:
		// "1000000000"
		System.out.println(Long.parseLong("1000000000")); // No problem, 1000000000
		// "10000000000"
		System.out.println(Long.parseLong("10000000000")); // No problem, 10000000000
		// "10000000000L"
		// 'l' or 'L' as a type indicator are not permitted here, unlike a literal
//    System.out.println(Long.parseLong("10000000000L")); // NumberFormatException

		// float:
		// "10000000000"
		System.out.println(Float.parseFloat("10000000000")); // No problem, 1.0E10
		// "10000000000F"
		System.out.println(Float.parseFloat("10000000000F")); // No problem, 1.0E10
		// "314e-2"
		System.out.println(Float.parseFloat("314e-2")); // No problem, 3.14
		// "3.14D"
		System.out.println(Float.parseFloat("3.14D")); // No problem, 3.14
		// " 3.14 \n"
		System.out.println(Float.parseFloat("  3.14   \n")); // No problem, 3.14
		// null
//    System.out.println(Float.parseFloat(null)); // NullPointerException

		// boolean:
		// "true"
		System.out.println(Boolean.parseBoolean("true")); // No problem, true
		// "TrUe"
		System.out.println(Boolean.parseBoolean("TrUe")); // No problem, true
		// "false"
		System.out.println(Boolean.parseBoolean("false")); // No problem, false
		// "no"
		System.out.println(Boolean.parseBoolean("no")); // No problem, false
		// "giraffe"
		System.out.println(Boolean.parseBoolean("giraffe")); // No problem, false
		// null
		System.out.println(Boolean.parseBoolean(null)); // No problem, false

	}
}
```

`Lab 1 - NaNTest.java`
```java
public class NaNTest {

	public static void main(String[] args) {
		double f = 0.0 / 0.0;
		System.out.println(f);
		Double fObj = 0.0 / 0.0;
		System.out.println(fObj);
	}
}
```

`Lab 2a - AutoboxOverloada.java`
```java
public class AutoboxOverloada {
  public static void method(Object o) { System.out.println("In Object method"); }
  // a.: The method call compiles even though no method takes int.
  //     The int value is autoboxed to Integer, which is a subclass of Number.
  public static void method(Number n) { System.out.println("In Number method"); }
  //     Java will NOT both widen the int to long, then autobox to Long.
  public static void method(Long l)   { System.out.println("In Long method"); }

  public static void main(String[] args) {
    int var = 17;
    method(var);
  }
}
```

`Lab 2b - AutoboxOverload.java`
```java
public class AutoboxOverloadb {
  public static void method(Object o) { System.out.println("In Object method"); }
  public static void method(Number n) { System.out.println("In Number method"); }
  public static void method(Long l)   { System.out.println("In Long method"); }
  // b.: Java chooses the method taking long, preferring to widen the int to long
  //     rather than autoboxing to an Integer object.
  public static void method(long l)   { System.out.println("In long method"); }

  public static void main(String[] args) {
    int var = 17;
    method(var);
  }
}
```

`Lab 2c - AutoboxOverload.java`
```java
public class AutoboxOverloadc {
  public static void method(Object o) { System.out.println("In Object method"); }
  public static void method(Number n) { System.out.println("In Number method"); }
  public static void method(Long l)   { System.out.println("In Long method"); }
  public static void method(long l)   { System.out.println("In long method"); }
  // c.: Even with a method that takes Integer available, Java still chooses
  //     to widen int to long instead of autoboxing.
  public static void method(Integer i){ System.out.println("In Integer method"); }

  public static void main(String[] args) {
    int var = 17;
    method(var);
  }
}
```

`Lab 2d - AutoboxOverload.java`
```java
public class AutoboxOverloadd {
  public static void method(Object o) { System.out.println("In Object method"); }
  public static void method(Number n) { System.out.println("In Number method"); }
  public static void method(Long l)   { System.out.println("In Long method"); }
  public static void method(long l)   { System.out.println("In long method"); }
  public static void method(Integer i){ System.out.println("In Integer method"); }
  // d.: Of course now Java will choose the method taking int.
  public static void method(int i)    { System.out.println("In int method"); }

  public static void main(String[] args) {
    int var = 17;
    method(var);
  }
}
```

`Lab 3 - CountUpOrDown.java`
```java
public class CountUpOrDown {

	public static void main(String[] args) {

		Scanner input = new Scanner(System.in);

		System.out.print("Please enter a whole number: ");
		int count = input.nextInt();
		System.out.print("Please enter true or false: ");
		boolean b = input.nextBoolean();

		if (b) {
			for (int i = 0; i <= count; i++) {
				System.out.println(i);
			}
		} else {
			for (int i = count; i >= 0; i--) {
				System.out.println(i);
			}
		}

		input.close();
	}
}
```

`Lab 4 - IntegerReferences.java`
```java
public class IntegerReferences {
	public static void main(String[] args) {
		Integer i = Integer.valueOf(1000);
		increment(i);
		// This prints 1000. The local variable i in main still refers
		// to the immutable Integer object created on line 5.
		System.out.println(i);

		// If we assign the Integer reference returned by increment()
		// to our local variable, it will print 1001.
		i = increment(i);
		System.out.println(i);

	}

	private static Integer increment(Integer i) {
		// This statement does not modify the contents of the passed Integer,
		// which is immutable. Instead, it unboxes the value to an in, increments,
		// then autoboxes the result as a new Integer.
		i++;
		return i;
	}
}
```

`Lab 5 - TestLetters.java`
```java
public class TestLetters {

	public static void main(String[] args) {
		Scanner input = new Scanner(System.in);
		System.out.print("Enter some text: ");
		String text = input.nextLine();
		input.close();
		TestLetters tester = new TestLetters();
		tester.test(text);
	}

	private void test(String text) {
		char[] chars = text.toCharArray();
		for (char c : chars) {
			System.out.print(c);
			if (Character.isUpperCase(c)) {
				System.out.print(" is uppercase.");
			} else if (Character.isLowerCase(c)) {
				System.out.print(" is lowercase.");
			} else if (Character.isDigit(c)) {
				System.out.print(" is a digit.");
			}
			System.out.println();
		}
	}
}
```

#### Interfaces
1. Interfaces
2. Declaring an Interface
3. Using Interfaces
4. Labs - Declaring and Using Interfaces

`Lab 1 - Drawable.java`

```java

```

`Lab 2 - Circle.java`

```java

```

`Lab 3 - Rectangle.java`

```java

```

`Lab 4 - DrawableTester.java `

```java

```

`Lab 5 - Text.java`

```java

```

#### Project: Lord of the Objects