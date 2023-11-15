## [Week 3](https://github.com/SkillDistillery/SD41/blob/main/java1/README.md)

### Java Libraries

### Week 3 - Day 1

#### Generics and ArrayList
1. Arrays Revisited
2. The ArrayList Class
3. Generic <Types>
4. ArrayList - Adding and Getting
5. Replacing, Inserting, and Removing
6. Array vs. ArrayList
7. ArrayList - Size vs. Capacity *
8. Labs

`GenericsAndArrayList/com.skilldistillery.generics.drills.ArrayListExample`

```java
import java.util.ArrayList;

public class ArrayListExample {

	public static void main(String[] args) {
		ArrayListExample ex = new ArrayListExample();
		ex.run();
	}

	private void run() {
		// Declare and instantiate an ArrayList to hold Strings.
		// Use the type argument <String> in the constructor call.
		ArrayList<String> strings = new ArrayList<String>();

		// Declare and instantiate an ArrayList to hold Double objects.
		// This time use the <> shortcut in the constructor call.
		ArrayList<Double> doubles = new ArrayList<>();

		// Try to declare an ArrayList to hold double primitives (not Double objects).
		// What happens?
		// ArrayList<double> dubs;

		// Now try declaring an ArrayList without type arguments.
		ArrayList noType = new ArrayList();

		// What is the warning Eclipse gives you?
		// "ArrayList is a raw type. References to generic type ArrayList<E> should be
		// parameterized"

		// What combinations of <> and <String> can you put on either side of the =, and
		// still have the code compile?
		ArrayList<String> list1 = new ArrayList();
		ArrayList list2 = new ArrayList<>();
	}
}
```

`GenericsAndArrayList/com.skilldistillery.generics.drills.Container`

```java
public class Container<E> {
	private E field;

	public void set(E obj) {
		this.field = obj;
	}

	public E get() {
		return field;
	}
}
```

`GenericsAndArrayList/com.skilldistillery.generics.drills.GenericContainer`

```java
import java.util.ArrayList;

import com.skilldistillery.generics.solutions.Container;

public class GenericContainer {

	public static void main(String[] args) {

		// Declare and instantiate a Container to hold a Character object.
		Container<Character> cont = new Container<>();

		// Call the object's set method and pass in 'A'.
		cont.set('A'); // autoboxing

		// get the Character from the object and pass it to printChar.
		printChar(cont.get());

		// Try to set an Integer or String into the object.
		// cont.set("a"); // String will not work
		// cont.set(new Integer(1)); // Integer will not work

		// Create an ArrayList to hold Integer objects.
		ArrayList<Integer> list = new ArrayList<Integer>();

		// Optional: can you create an ArrayList to hold Container<Character> objects?
		ArrayList<Container<Character>> contList = new ArrayList<>();
	}

	private static void printChar(Character c) {
		System.out.println("The character is " + c);
	}
}
```

`GenericsAndArrayList/com.skilldistillery.generics.drills.AddingAndGetting`

```java
import java.util.ArrayList;

public class AddingAndGetting {

	public static void main(String[] args) {
		AddingAndGetting ag = new AddingAndGetting();
		ag.run();
	}

	private void run() {
		ArrayList<String> strings = new ArrayList<>();

		// Output the list's size.
		System.out.println("Size is " + strings.size());

		// Add first names of several of your classmates.
		strings.add("Belinda");
		strings.add("Jane");
		strings.add("Charlotte");
		strings.add("Gina");

		// Output the list's size again.
		System.out.println("Size is now " + strings.size());

		// Use a for loop and get(index) to iterate through the list and print each name
		// in uppercase letters.
		for (int i = 0; i < strings.size(); i++) {
			String n = strings.get(i);
			System.out.println(n.toUpperCase());
		}

		outputLastItem(strings); // Stretch goal: Finish the method below.

	}

	private void outputLastItem(ArrayList<String> list) {
		// Finish this method to output the last item in the list in lowercase.
		String last = list.get(list.size() - 1);
		System.out.println(last.toLowerCase());
	}
```

`GenericsAndArrayList/com.skilldistillery.generics.drills.ChangingArrayList`

```java
import java.util.ArrayList;

public class ChangingArrayList {
	public static void main(String[] args) {
		ChangingArrayList cal = new ChangingArrayList();
		cal.run();
	}

	private void run() {
		ArrayList<String> namesList = new ArrayList<>();

		namesList.add("Alice");
		namesList.add("Queen of Hearts");
		namesList.add("Cheshire Cat");
		namesList.add("Mad Hatter");
		namesList.add("Tweedle Dee");
		namesList.add("Tweedle Dum");

		System.out.println("There are " + namesList.size() + " elements in the list.");
		System.out.println(namesList); // calls toString() for each element

		// Remove Queen of Hearts and store the String in a variable.
		String queen = namesList.remove(1);

		// Output the contents of namesList with System.out.println()
		System.out.println(namesList);

		// Output the size of namesList
		System.out.println("List size is " + namesList.size());

		// Insert Queen of Hearts between Tweedle Dee and Tweedle Dum
		namesList.add(4, queen);

		// Output the contents of namesList
		System.out.println(namesList);

		// Replace Mad Hatter with Dormouse
		namesList.set(2, "Dormouse");

		// Output the contents of namesList
		System.out.println(namesList);

		// Remove Cheshire Cat
		namesList.remove(1);

		System.out.println(namesList);

		printMessage(namesList);
	}

	// This method uses the contents of your ArrayList
	private void printMessage(ArrayList<String> list) {
		if (list.size() != 5) {
			return;
		}
		String output = "";
		int i = 0, index[] = { 0, 7, 4, 2, 7 };
		int delta[] = { 5, 0, 1, -1, 0 };
		for (String string : list) {
			output += (char) (string.charAt(index[i]) + delta[i++]);
		}
		for (int j = 0; j < list.size(); j++) {
			char c = '\u0000';
			switch (j) {
			case 0:
				c = (char) (list.get(j).charAt(0) + 24);
				break;
			case 1:
				c = list.get(j).charAt(4);
				break;
			case 2:
				c = (char) (list.get(j).charAt(1) - 2);
				break;
			case 3:
				c = (char) (list.get(j).charAt(1) - 3);
				break;
			case 4:
				c = (char) (list.get(j).charAt(12 - 5));
				break;
			}
			output += c;
		}
		i = 0;
		index = new int[] { 2, 7, 3, 11, 0 };
		delta = new int[] { -33, 0, -4, 3, -38 };
		for (String s : list) {
			output += (char) (s.charAt(index[i]) + delta[i++]);
		}
		System.out.println(output);
	}
}
```

`Lab 3 - Stack.java`

```java
import java.util.ArrayList;

/**
 * Note: this Stack implementation has an issue, in that we could add nulls, but
 * we also return null for an empty list. We will have to live with this.
 * 
 */
public class Stack<E> {
	private ArrayList<E> list = new ArrayList<>();

	public Stack() {

	}

	public E push(E item) {
		list.add(item);
		return item;
	}

	public E pop() {
		if (list.size() == 0) {
			return null;
		}
		return list.remove(list.size() - 1);
	}

	public E peek() {
		if (list.size() == 0) {
			return null;
		}
		return list.get(list.size() - 1);
	}

	public int search(Object o) {
		int index = -1;
		for (int i = 0; i < list.size(); i++) {
			E item = list.get(i);
			if (item.equals(o)) {
				index = i;
				break;
			}
		}
		return index;
	}
}
```

`Lab 3 - StackTests.java`

```java
import static org.junit.Assert.*;

import org.junit.After;
import org.junit.Before;
import org.junit.Test;

public class StackTests {

  private Stack<String> stack;
  
  @Before
  public void setUp() throws Exception {
    stack = new Stack<>();
  }

  @After
  public void tearDown() throws Exception {
    stack = null;
  }

  @Test
  public void test_push_adds_to_stack_and_pop_removes_in_order() {
    stack.push("A");
    stack.push("B");
    stack.push("C");
    assertEquals("C", stack.pop());
    assertEquals("B", stack.pop());
    stack.push("D");
    assertEquals("D", stack.pop());
    assertEquals("A", stack.pop());
  }
  
  @Test
  public void test_push_adds_to_stack_and_peek_twice_shows_same_object_on_top_of_stack() {
    stack.push("A");
    stack.push("B");
    stack.push("C");
    assertEquals("C", stack.peek());
    assertEquals("C", stack.peek());
    assertEquals("C", stack.peek());
  }
  
  @Test
  public void test_pop_empty_stack_returns_null() {
    assertNull(stack.pop());
  }
  
  @Test
  public void test_peek_empty_stack_returns_null() {
    assertNull(stack.peek());
  }
}
```

#### The List Interface
1. The List Interface
2. List Methods
3. LinkedList
4. Vector
5. Using List - Best Practices
6. Labs

`ListInterface/com.skilldistillery.listinterface.drills.PlanetList`

```java
//Planet.java
import java.util.Objects;

public class Planet {
	private String name;
	private long orbit;
	private int diameter;

	public Planet(String name, long orbit, int diameter) {
		this.name = name;
		this.orbit = orbit;
		this.diameter = diameter;
	}

	public String getName() {
		return name;
	}

	public long getOrbit() {
		return orbit;
	}

	public int getDiameter() {
		return diameter;
	}

	@Override
	public int hashCode() {
		return Objects.hash(diameter, name, orbit);
	}

	@Override
	public boolean equals(Object obj) {
		if (this == obj)
			return true;
		if (obj == null)
			return false;
		if (getClass() != obj.getClass())
			return false;
		Planet other = (Planet) obj;
		return diameter == other.diameter && Objects.equals(name, other.name) && orbit == other.orbit;
	}

	@Override
	public String toString() {
		return "Planet [Name=" + name + ", Orbit=" + orbit + ", Diameter=" + diameter + "]";
	}
}
```

```java
//PlanetList.java
import java.util.List;

public class PlanetList {

	public static void main(String[] args) {
		PlanetList p = new PlanetList();
		p.run();
	}

	private void run() {
		List<Planet> planets = PlanetUtilities.getPlanets();
		System.out.println(planets);

		// Create a new Planet object using the Planet constructor call below.
		Planet jupiter = new Planet("Jupiter", 778_330_000, 142_984);

		// Print true or false for whether the List contains this planet
		System.out.println(planets.contains(jupiter));

		// If this was not what you expected, change the Planet class to support
		// comparison to other Planets. (Hint: what method does Java use to see if
		// one Object equals another Object?)

		// Try to find the index of this planet in the List, and print out that index.
		System.out.println(planets.indexOf(jupiter));

		// Now remove Jupiter by passing the object reference you created, and
		// print true or false for whether removing worked.
		boolean didRemove = planets.remove(jupiter);
		System.out.println(didRemove);
		
		for (Planet planet : planets) {
			System.out.println(planet);
		}
	}
}
```

```java
//PlanetUtilities.java
import java.util.ArrayList;
import java.util.List;

public class PlanetUtilities {
	public static List<Planet> getPlanets() {
		List<Planet> planets = new ArrayList<>();

		planets.add(new Planet("Mercury", 57_910_000, 4_880));
		planets.add(new Planet("Venus", 108_200_000, 12_103));
		planets.add(new Planet("Earth", 149_600_000, 12_756));
		planets.add(new Planet("Mars", 227_940_000, 6_794));
		planets.add(new Planet("Jupiter", 778_330_000, 142_984));
		planets.add(new Planet("Saturn", 1_429_400_000, 120_536));
		planets.add(new Planet("Uranus", 2_870_990_000L, 51_118));
		planets.add(new Planet("Neptune", 4_504_000_000L, 49_532));

		return planets;
	}
}
```

`ListInterface/com.skilldistillery.listinterface.drills.LinkedListAdding`

```java
import java.time.Duration;
import java.time.LocalDateTime;
import java.util.ArrayList;
import java.util.LinkedList;
import java.util.List;

public class LinkedListAdding {

  public static void main(String[] args) {
    LinkedListAdding app = new LinkedListAdding();
    app.run();
  }
  
  private void run() {
    // Run the program with ArrayList, and note the time taken.
    // Then change myList refer to a LinkedList, and run again.
    List<Planet> myList = new LinkedList<>();
    fillLargeList(myList);
  }
  
  
  /**
   * This method will fill a List, alternating between adding to the
   * beginning and end. It will also calculate and print the time this
   * operation takes.
   */
  private void fillLargeList(List<Planet> list){
    
    // Get the start time
    LocalDateTime start = LocalDateTime.now();  // You will learn about this class
    
    // fill the list, alternating between beginning and end.
    int numElements = 100_000;
    System.out.println("Adding to " + list.getClass().getSimpleName() + "...");
    for(int i=0; i < numElements; i++) {
      if(i % 2 == 0) {
        list.add(0, new Planet("EvenPlanet", 100, 100));
      }
      else {
        list.add(new Planet("OddPlanet", 100, 100));
      }
    }
    
    // Get the end time
    LocalDateTime end = LocalDateTime.now();
    
    // Duration can calculate time elapsed
    Duration d = Duration.between(start, end);
    System.out.println(d.toMillis() + " milliseconds");
  }
}
```

`ListInterface/com.skilldistillery.listinterface.drills.LinkedListPositionalAccess`

```java
import java.time.Duration;
import java.time.LocalDateTime;
import java.util.ArrayList;
import java.util.LinkedList;
import java.util.List;

public class LinkedListPositionalAccess {

	public static void main(String[] args) {
		LinkedListPositionalAccess app = new LinkedListPositionalAccess();
		app.run();

	}

	private void run() {
		// Run the program with ArrayList, and note the time taken.
		// Then change myList refer to a LinkedList, and run again.
		List<Planet> list = new LinkedList<>();

		fillLargeList(list);

		// Get an element
		getFromList(list);
	}

	private void getFromList(List<Planet> list) {
		int size = list.size();
		int index = size * 3 / 4;
		System.out.println("Getting element from " + list.getClass().getSimpleName() + " index " + index);

		// Get the start time
		LocalDateTime start = LocalDateTime.now(); // You will learn about this class

		list.get(index);

		// Get the end time
		LocalDateTime end = LocalDateTime.now();

		// Duration can calculate time elapsed
		Duration d = Duration.between(start, end);
		System.out.println(list.getClass().getSimpleName() + " " + d.toMillis() + " milliseconds");
	}

	private void fillLargeList(List<Planet> list) {
		int numElements = 10_000_000;
		System.out.println("Adding to " + list.getClass().getSimpleName() + "...");
		for (int i = 0; i < numElements; i++) {
			list.add(new Planet("Planet", 100, 100));
		}
	}
}
```

`Lab 1 - NumbersList.java`

```java
import java.util.LinkedList;
import java.util.List;

public class NumbersList {
	public static void main(String[] args) {
		NumbersList nl = new NumbersList();
		nl.run();
	}

	private void run() {
		List<Integer> numbers = new LinkedList<>();

		for (int i = 0; i < 10; i++) {
			numbers.add((int) (10 + Math.random() * (90 + 1)));
		}

		System.out.println(numbers);
	}
}
```

`Lab 2 - SortNumbersList.java`

```java
import java.util.LinkedList;
import java.util.List;

public class SortNumbersList {
	public static void main(String[] args) {
		SortNumbersList snl = new SortNumbersList();
		snl.run();
	}

	private void run() {
		List<Integer> numbers = new LinkedList<>();

		for (int i = 0; i < 10; i++) {
			numbers.add((int) (10 + Math.random() * (90 + 1)));
		}

		System.out.println("Before Sort:");
		System.out.println(numbers);

		sortAndPrintList(numbers);
	}

	private void sortAndPrintList(List<Integer> numbers) {
		// bubbleSort(numbers);
		insertionSort(numbers);
		System.out.println("After sort");
		System.out.println(numbers);
	}

	private void bubbleSort(List<Integer> nums) {
		boolean swapped = true;
		while (swapped) {
			swapped = false;
			for (int i = 0; i < nums.size() - 1; i++) {
				if (nums.get(i) > nums.get(i + 1)) {
					// swap elements
					int temp = nums.get(i);
					nums.set(i, nums.get(i + 1));
					nums.set(i + 1, temp);
					swapped = true;
				}
			}
		}
	}

	private void insertionSort(List<Integer> nums) {
		for (int i = 1; i < nums.size(); i++) {
			int temp = nums.get(i);
			int j = i;

			while (j > 0 && nums.get(j - 1) > temp) {
				nums.set(j, nums.get(j - 1));
				j--;
			}
			nums.set(j, temp);
		}

	}
}
```

#### Exceptions
1. Introduction to Exceptions
2. The Exception Class
3. Checked Exceptions
4. Labs - Handling Exceptions
5. The Throwable Hierarchy *
6. Throwing Your Own Exceptions *
7. Exceptions and Inheritance *
8. finally
9. Labs *

`Exceptions/com.skilldistillery.exceptions.drills.TryCatchDrill`

```java
package com.skilldistillery.exceptions.drills;

import java.util.InputMismatchException;

import java.util.Scanner;

public class TryCatchDrill {

	public static void main(String[] args) {
		TryCatchDrill drill = new TryCatchDrill();
		Scanner scanner = new Scanner(System.in);
		drill.launch(scanner);
		scanner.close();

	}

	private void launch(Scanner scanner) {
		String keepGoing = "Y";
		while (keepGoing.toUpperCase().equals("Y")) {
			System.out.print("Enter a whole number: ");
			try {
				int number = scanner.nextInt();
				if (number % 2 == 0) {
					System.out.println(number + " is even.");
				} else {
					System.out.println(number + " is odd.");
				}
			} catch (InputMismatchException e) {
				System.out.println("Invalid input.");
				scanner.nextLine(); // Clear input buffer
			}
			System.out.print("Keep going? (Y/N)");
			keepGoing = scanner.next();
		}
	}
}
```

`Exceptions/com.skilldistillery.exceptions.drills.TryCatchDrill`

```java
package com.skilldistillery.exceptions.drills;

import java.util.InputMismatchException;

import java.util.Scanner;

public class TryCatchDrill {

	public static void main(String[] args) {
		TryCatchDrill drill = new TryCatchDrill();
		Scanner scanner = new Scanner(System.in);
		drill.launch(scanner);
		scanner.close();

	}

	private void launch(Scanner scanner) {
		String keepGoing = "Y";
		while (keepGoing.toUpperCase().equals("Y")) {
			System.out.print("Enter a whole number: ");
			try {
				int number = scanner.nextInt();
				if (number % 2 == 0) {
					System.out.println(number + " is even.");
				} else {
					System.out.println(number + " is odd.");
				}
			} catch (InputMismatchException e) {
				System.err.println("Invalid input.");
				scanner.nextLine(); // Clear input buffer
			}
			System.out.print("Keep going? (Y/N)");
			keepGoing = scanner.next();
		}
	}
}
```

`ErrorDrill.java`

```java
public class ErrorDrill {
	private static int callCount;

	public static void main(String[] args) {
		ErrorDrill drill = new ErrorDrill();
		drill.callMe();
	}

	private void callMe() {
		// 1. Increment callCount
		callCount++;

		// 2. Print out callCount
		System.out.println(callCount);

		// 3. Call callMe()
		this.callMe();

		// 4. Print "callMe finished."
		System.out.println("callMe finished.");
	}
}
```

`Exceptions/com.skilldistillery.exceptions.drills.TryCatchDrill`

```java
import java.util.InputMismatchException;
import java.util.Scanner;

public class TryCatchDrill {

	public static void main(String[] args) {
		TryCatchDrill drill = new TryCatchDrill();
		Scanner scanner = new Scanner(System.in);
		drill.launch(scanner);
		scanner.close();
	}

	private void launch(Scanner scanner) {
		String keepGoing = "Y";
		while (keepGoing.toUpperCase().equals("Y")) {
			System.out.print("Enter a whole number: ");
			try {
				int number = scanner.nextInt();
				if (number % 2 == 0) {
					System.out.println(number + " is even.");
				} else {
					System.out.println(number + " is odd.");
				}
			} catch (InputMismatchException e) {
				System.out.println("Invalid input.");
				scanner.nextLine(); // Clear input buffer
			}
			System.out.print("Keep going? (Y/N)");
			keepGoing = scanner.next();
		}
	}
}
```

`Lab 1 - Circle.java`

```java
import static java.lang.Math.*;

public class Circle extends Shape {
	double radius;

	public double getRadius() {
		return radius;
	}

	public void setRadius(double radius) {
		if (radius <= 0) {
			throw new IllegalArgumentException("Radius must be greater than zero.");
		}
		this.radius = radius;

	}

	@Override
	public double getArea() {
		return PI * pow(radius, 2);
	}

	public Circle(double radius) {
		super();
		this.setRadius(radius);
	}

	public Circle() {
		super();
	}

	public Circle(int xCoordinate, int yCoordinate) {
		super(xCoordinate, yCoordinate);
	}

	public Circle(int xCoordinate, int yCoordinate, double radius) {
		super(xCoordinate, yCoordinate);
		this.setRadius(radius);
	}

	@Override
	public String toString() {
		StringBuilder builder = new StringBuilder();
		builder.append("Circle [radius=").append(radius).append("]");
		return builder.toString();
	}
}
```

`Lab 1 - Rectangle.java`

```java
public class Rectangle extends Shape {
	double width;
	double height;

	public double getWidth() {
		return width;
	}

	public void setWidth(double width) {
		if (width <= 0) {
			throw new IllegalArgumentException("Width must be greater than zero.");
		}
	  this.width = width;
  }

	public double getHeight() {
		return height;
	}

	public void setHeight(double height) {
		if (height <= 0) {
			throw new IllegalArgumentException("Height must be greater than zero.");
		}
		this.height = height;
	}

	@Override
	public double getArea() {
		return width * height;
	}

	public Rectangle(double width, double height) {
		super();
		this.setWidth(width);
		this.setHeight(height);
	}

	public Rectangle() {
		super();
	}

	public Rectangle(int xCoordinate, int yCoordinate) {
		super(xCoordinate, yCoordinate);
	}

	public Rectangle(int xCoordinate, int yCoordinate, double width, double height) {
		super(xCoordinate, yCoordinate);
		this.setWidth(width);
		this.setHeight(height);
	}

	@Override
	public String toString() {
		StringBuilder builder = new StringBuilder();
		builder.append("Rectangle [width=").append(width).append(", height=").append(height).append("]");
		return builder.toString();
	}

	@Override
	public int hashCode() {
		final int prime = 31;
		int result = 1;
		long temp;
		temp = Double.doubleToLongBits(height);
		result = prime * result + (int) (temp ^ (temp >>> 32));
		temp = Double.doubleToLongBits(width);
		result = prime * result + (int) (temp ^ (temp >>> 32));
		return result;
	}

	@Override
	public boolean equals(Object obj) {
		if (this == obj)
			return true;
		if (obj == null)
			return false;
		if (getClass() != obj.getClass())
			return false;
		Rectangle other = (Rectangle) obj;
		if (Double.doubleToLongBits(height) != Double.doubleToLongBits(other.height))
			return false;
		if (Double.doubleToLongBits(width) != Double.doubleToLongBits(other.width))
			return false;
		return true;
	}
}
```

`Lab 1 - ShapeTester.java`

```java
public class ShapeTester {
  private Shape[] shapes;

  public static void main(String[] args) {
    ShapeTester tester = new ShapeTester();
    tester.test();
  }

  private void test() {
    shapes = new Shape[10];
    
    shapes[0] = new Circle(2.2);
    shapes[1] = new Rectangle(2.0, 4.0);
    shapes[2] = new Circle(0);  // Exception in thread "main" java.lang.IllegalArgumentException: Radius must be greater than zero.
    // Execution stops, and the exception propagates to main() and then to the JVM, which exits.
    shapes[3] = new Rectangle(3.0, -5.0);
    shapes[4] = new Rectangle(17.7, 31.1);
    
    printShapes(shapes);
  }

  private void printShapes(Shape[] shapes) {
    for (Shape shape : shapes) {
      if (shape != null) {
        System.out.println(shape + ", area="+shape.getArea());
      }
    }
  }
}
```

`Lab 2 - ShapeTester.java`

```java
public class ShapeTester {
	private Shape[] shapes;

	public static void main(String[] args) {
		ShapeTester tester = new ShapeTester();
		tester.test();
	}

	private void test() {
		shapes = new Shape[10];

		try {
			shapes[0] = new Circle(2.2);
			shapes[1] = new Rectangle(2.0, 4.0);
			shapes[2] = new Circle(0); // Exception in thread "main" java.lang.IllegalArgumentException: Radius must be
										// greater than zero.
			// Execution stops, and the exception propagates to main() and then to the JVM,
			// which exits.
			shapes[3] = new Rectangle(3.0, -5.0);
			shapes[4] = new Rectangle(17.7, 31.1);
		} catch (IllegalArgumentException e) {
			System.err.println(e.getMessage());
		}

		printShapes(shapes);
	}

	private void printShapes(Shape[] shapes) {
		for (Shape shape : shapes) {
			if (shape != null) {
				System.out.println(shape + ", area=" + shape.getArea());
			}
		}
	}
}
```

`Lab 3 - ShapeTester.java`

```java
public class ShapeTester {
	private Shape[] shapes;

	public static void main(String[] args) {
		ShapeTester tester = new ShapeTester();
		tester.test();
	}

	private void test() {
		shapes = new Shape[10];

		try {
			shapes[0] = new Circle(2.2);
		} catch (IllegalArgumentException e) {
			System.err.println(e.getMessage());
		}

		try {
			shapes[1] = new Rectangle(2.0, 4.0);
		} catch (IllegalArgumentException e) {
			System.err.println(e.getMessage());
		}

		try {
			shapes[2] = new Circle(0); // Exception in thread "main" java.lang.IllegalArgumentException: Radius must be
		} catch (IllegalArgumentException e) {
			System.err.println(e.getMessage());
		}

		// greater than zero.
		// Execution stops, and the exception propagates to main() and then to the JVM,
		// which exits.

		try {
			shapes[3] = new Rectangle(3.0, -5.0);
		} catch (IllegalArgumentException e) {
			System.err.println(e.getMessage());
		}

		try {
			shapes[4] = new Rectangle(17.7, 31.1);
		} catch (IllegalArgumentException e) {
			System.err.println(e.getMessage());
		}

		printShapes(shapes);
	}

	private void printShapes(Shape[] shapes) {
		for (Shape shape : shapes) {
			if (shape != null) {
				System.out.println(shape + ", area=" + shape.getArea());
			}
		}
	}
}
```

`Lab 4 - Circle.java`

```java

```

`Lab 4 - Rectangle.java`

```java

```

`Lab 4 - ShapeTester.java`

```java

```

#### Project: Data Entry with Exceptions

### Week 3 - Day 2

#### Testing Exceptions with JUnit
1. JUnit and Exceptions
2. Testing Exceptions with try and catch
3. Labs

```java

```

#### Input/Output Streams
1. Overview of Streams
2. File Object
3. BufferedReader
4. PrintStream and PrintWriter
5. Closing Streams
6. Labs

`Lab 1 - SearchEmployees.java`

```java

```

`Lab 2 - PlanetReader.java`

```java

```

`Lab 3 - PlanetReader2.java`

```java

```

`Lab 4 - SearchEmployees.java`

```java

```

#### The Set Interface
1. The Set Interface
2. Set Implementation Classes - HashSet and LinkedHashSet
3. Iterator Explained *
4. SortedSet Interface and TreeSet Class
5. Collection Superinterface
6. Labs

`SetInterface/com.skilldistillery.setinterface.drills.SetTest`

```java
import java.util.HashSet;
import java.util.Iterator;
import java.util.Set;

public class SetTest {

  public static void main(String[] args) {
    SetTest st = new SetTest();
    st.launch();
  }
  
  public void launch() {
    Album al1 = new Album(1, "The Beatles", "The Beatles 1");
    Album al2 = new Album(2, "Prince", "The Very Best of Prince");
    Album al3 = new Album(3, "AC/DC", "Let There Be Rock");
    Album al4 = new Album(3, "AC/DC", "Let There Be Rock");
    
    Set<Album> albumCollection = new HashSet<>();
    
    // Place each call to add in a System.out.println() and run
    // the application. 
    System.out.println(albumCollection.add(al1));
    System.out.println(albumCollection.add(al2));
    System.out.println(albumCollection.add(al3));
    System.out.println(albumCollection.add(al4));
    
//    albumCollection.add(al1);
//    albumCollection.add(al2);
//    albumCollection.add(al3);
//    albumCollection.add(al4); //Doesn't get added because duplicate only store unique elements.
    
    printAlbums(albumCollection);
  }
  
  private void printAlbums(Set<Album> collection) {
    Iterator<Album> it = collection.iterator();
    while (it.hasNext()) {
      System.out.println(it.next());
    }
  }
}
```

`SetInterface/com.skilldistillery.setinterface.drills.SportsTeamApp`

```java
import java.util.HashSet;
import java.util.Iterator;
import java.util.Set;

public class SportsTeamApp {

	public static void main(String[] args) {
		SportsTeamApp app = new SportsTeamApp();
		app.launch();
	}

	private void launch() {
		SportsTeam t1 = new SportsTeam("Denver", "Vampires");
		SportsTeam t2 = new SportsTeam("Michigan", "Werewolves");
		SportsTeam t3 = new SportsTeam("Derry", "Clowns");
		SportsTeam t4 = new SportsTeam("Derry", "Clowns");
		SportsTeam t5 = new SportsTeam("Houston", "Chupacabras");

		Set<SportsTeam> teams = new HashSet<>();
		addTeam(teams, t1);
		addTeam(teams, t2);
		addTeam(teams, t3);
		addTeam(teams, t4);
		addTeam(teams, t5);

		// Iterate through the contents of the Set using an iterator, and print them to
		// the screen.
		Iterator<SportsTeam> st = teams.iterator();
		while (st.hasNext()) {
			SportsTeam s = st.next();
			System.out.println(s);
		}

		// If the results are not as expected, fix SportsTeam.
	}

	// Change addTeam() to add the object to the Set.
	private void addTeam(Set<SportsTeam> set, SportsTeam t) {
		boolean added = set.add(t);
		System.out.println(t.getName() + " added: " + added);
	}
}
```

`SetInterface/com.skilldistillery.setinterface.drills.CollectionTest`

```java
import java.util.ArrayList;
import java.util.Collection;
import java.util.HashSet;

public class CollectionTest {

	public static void main(String[] args) {
		// Assign an ArrayList to c1
		Collection<String> c1 = new ArrayList<>();

		// Add four Strings to c1 - your choice of Strings.
		c1.add("A");
		c1.add("B");
		c1.add("C");
		c1.add("D");

		// Call addAll(c1) on c1; you are trying to add the elements of c1
		// to what is already in c1. Store the result of addAll in a variable
		// and print it to the screen.
		boolean result = c1.addAll(c1);

		// Collection classes have good toString() methods, so we will use
		// System.out.println() to see the contents.
		System.out.println("Contents of c1: " + c1);
		System.out.println("Result of addAll is " + result);

		// Repeat the process with c2, using a HashSet
		Collection<String> c2 = new HashSet<>();
		c2.add("D");
		c2.add("E");
		c2.add("F");
		c2.add("G");

		result = c2.addAll(c1);

		System.out.println("Contents of c2: " + c2);
		System.out.println("Result is " + result);
	}
}
```

`Lab 1 - NameApp.java`

```java
import java.io.BufferedReader;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;
import java.util.ArrayList;
import java.util.HashSet;
import java.util.List;
import java.util.Set;

public class NameApp {

	public static void main(String[] args) {
		NameApp nA = new NameApp();
		nA.run();
	}

	public void run() {
		// Initializes two collections: A List named 'listToFill' and a Set named
		// 'setToFill'
		List<String> listFill = new ArrayList<String>();
		Set<String> setFill = new HashSet<>();

		// Call the readNamesIntoCollections method, passing in the two collections
		// (listToFill and setToFill)
		// as arguments and assigns the returned number of lines to the variable
		// numLines.
		int numLines = namesInCollection(listFill, setFill);

		// Print the sizes of the List and Set to the console, as well as the number of
		// lines in the file.
		System.out.println("List Size: " + listFill.size());
		System.out.println("Set Size: " + setFill.size());
		System.out.println("Lines in File: " + numLines);
	}

	// Define a private method 2 args: 'List<String> namesList, Set<String>
	// namesSet'
	private int namesInCollection(List<String> namesList, Set<String> namesSet) {
		// Initialize a variable numLines to 0 and declare a BufferedReader named reader
		// and set it to null.
		BufferedReader reader = null;
		int numLines = 0;
		try {
			reader = new BufferedReader(new FileReader("names.txt"));
			String line;
			// While line !=null it adds each line to both namesList and namesSet, and
			// increments numLines.
			while ((line = reader.readLine()) != null) {
				namesList.add(line);
				namesSet.add(line);
				numLines++;
			}
			// When the program tries to open a file that doesn't exist at the specified
			// path.
		} catch (FileNotFoundException e) {
			e.printStackTrace();
			// General Exception.
		} catch (IOException e) {
			e.printStackTrace();
			// Object that is null.
		} finally {
			if (reader != null) {
				try {
					reader.close();
				} catch (IOException e) {
					e.printStackTrace();
				}
			}
		}
		return numLines;
	}
}
```

#### Project: Name Separator App

### Week 3 - Day 3

#### Garbage Collection
1. Objects on the Heap
2. Garbage Collection
3. Memory Management Strategies
4. The finalize method
5. Understanding Garbage Collection
6. Labs


```java

```

#### Debugging Programs
1. What is Debugging?
2. Commenting Out Code
3. Manual Output in Code
4. Making Debugging Print Statements Conditional
5. Tools to Debug Programs
6. Debugging in Eclipse
7. The Debug Perspective
8. Breakpoints
9. Examining Variables
10. Controlling Program Execution
11. Labs


```java

```

#### Homework Project: Jets

### Week 3 - Day 4

#### Regular Expressions
1. Introducing Regular Expressions
2. Options
3. Literals and Wild Cards
4. Assertions
5. Quantifiers
6. Labs 1
7. Grouping and Alternatives
8. Labs 2


```java

```

#### Regular Expressions in Java
1. Regular Expressions in Java
2. The Pattern Class
3. The Matcher Class
4. Capturing Groups
5. String Methods That Use Regular Expressions
6. Labs


```java

```

#### The Map Interface
1. The Map Collection
2. Map Implementation Class - HashMap
3. Map Implementation Classes - Hashtable, LinkedHashMap, and TreeMap
4. When to Use a Map *
5. Labs

```java

```

#### Project: Project: Pig Latin

#### Project: Project: Declaration of Independence

### Week 3 - Day 5

#### Collection Sorting and Tuning
1. Sorting with Comparable
2. Sorting with Comparator
3. Sorting Lists
4. Sorting Maps
5. Sorting Arrays
6. Collections Utility Methods
7. Labs

```java

```

#### Project: Lottery: NBA Draft

#### Project: Lottery: Powerball

### Week 3 - Day 6

#### HashMap Internals
1. Keys and hashCode
2. Hash Buckets
3. Map Entries
4. Tuning HashMap
5. Labs


```java

```

#### Project: Project: Mad Libs

### Week 3 - Day 7

#### The Java Virtual Machine
1. The Java Virtual Machine
2. The Java Runtime Environment
3. The Java Development Kit
4. The Java Language Specification
5. Labs


```java

```

#### The args Array
1. The main Method
2. The args Array
3. Handling Command-Line Arguments
4. Testing args In Eclipse
5. Labs


```java

```

#### Intermediate Interfaces
1. Smart Home - Part 2
2. Interface Fields
3. Interface Inheritance
4. Static Interface Methods
5. Interface Default Methods
6. Multiple Inheritance
7. Labs


```java

```

#### Project: Roman Numerals

#### Project: Project: White Rabbit

### Week 3 - Day 8

#### Enumerated Types
1. enum Types
2. enum Details
3. Using enum
4. enum Methods
5. enum Members
6. Labs

``

```java

```

#### Homework Project: Blackjack

### Week 3 - Day 9

#### Dates and Times
1. Temporal Data
2. LocalDate
3. LocalTime
4. Date-Times and Instant
5. Duration and Period
6. DateTimeFormatter
7. Labs


```java

```

#### Project: History

#### Project: Working with Dates and Times

#### Inner Classes
1. Inner Classes
2. Member Classes
3. Local Classes
4. Anonymous Classes
5. Anonymous Classes and Interfaces
6. Instance Initializers
7. Compiling Inner Classes
8. Labs

```java

```

#### Project: Sorting and Filtering with Inner Classes

### Week 3 - Day 10

#### Introduction to Lambda Expressions
1. Inner Classes Review
2. Lambda Expressions
3. Translating Inner Classes to Lambdas
4. Lambda Rules and Syntax
5. Lambdas and Interfaces
6. Predicate<T> Functional Interface *
7. Standard Functional Interfaces *
8. Labs *

#### Project: Sorting and Filtering with Lambdas

#### Lambda Examples

### Week 3 - Day 11

#### JUnit 5
1. Introduction
2. Test Cases
3. Test Case Setup
4. Test Method Names
5. Assertions
6. Testing Exceptions
7. Labs

