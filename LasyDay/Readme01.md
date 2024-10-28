Here's a quick Java cheatsheet covering these topics:

---

### 1. **Data Types, Variables, Constants, Operators, and Casting**

- **Data Types**: 
  - Primitive: `int`, `float`, `double`, `boolean`, `char`, `long`, `short`, `byte`
  - Non-Primitive: `String`, `Array`, `Class`, `Interface`

- **Variables**: `type variableName = value;`
  - Example: `int age = 25;`

- **Constants**: Use `final` keyword.
  - Example: `final double PI = 3.14159;`

- **Operators**: 
  - Arithmetic: `+`, `-`, `*`, `/`, `%`
  - Relational: `==`, `!=`, `<`, `>`, `<=`, `>=`
  - Logical: `&&`, `||`, `!`
  - Assignment: `=`, `+=`, `-=`, `*=`, `/=`

- **Casting**:
  - Widening (automatic): `int x = 5; double y = x;`
  - Narrowing (explicit): `double y = 5.5; int x = (int) y;`

### 2. **String Class**

- Immutable, used for string manipulation.
- Common methods: `.length()`, `.substring()`, `.charAt(index)`, `.equals()`, `.compareTo()`, `.toUpperCase()`, `.toLowerCase()`, `.trim()`

### 3. **Conditional Statements and Visibility**

- **Conditional Statements**:
  - `if`, `else if`, `else`
  - `switch(expression) { case value: ... break; }`

- **Visibility (Access Modifiers)**:
  - `public`: accessible everywhere
  - `protected`: accessible in the same package or subclasses
  - `default`: accessible within the same package only
  - `private`: accessible only within the class

### 4. **Loops**

- `for`: `for (int i = 0; i < 10; i++)`
- `while`: `while (condition)`
- `do-while`: `do { ... } while (condition);`
- Enhanced `for`: `for (Type item : collection)`

### 5. **Arrays**

- Declaration: `int[] array = new int[5];`
- Access elements: `array[0] = 10;`
- Length: `array.length`

### 6. **OOP (Class, Object, State, Behavior)**

- **Class**: Template for creating objects
  - Example: `class Car { ... }`
  
- **Object**: Instance of a class
  - Example: `Car myCar = new Car();`

- **State**: Represented by fields (variables)
- **Behavior**: Represented by methods

### 7. **Fields, Methods, Constructors, Packages, Imports**

- **Fields**: Variables in a class
  - Example: `private String name;`
  
- **Methods**: Functions within a class
  - Example: `public void drive() { ... }`
  
- **Constructors**: Initialize objects
  - Example: `public Car(String model) { this.model = model; }`
  
- **Packages**: Organize classes
  - Example: `package mypackage;`
  
- **Imports**: Include other classes
  - Example: `import java.util.Scanner;`

### 8. **Varargs**

- Allows passing variable number of arguments
  - Example: `public void printNames(String... names) { for (String name : names) { System.out.println(name); } }`

### 9. **Date and Time**

- `LocalDate`, `LocalTime`, `LocalDateTime`, `Instant`, `Duration`, `Period`
- Example:
  ```java
  LocalDate date = LocalDate.now();
  LocalTime time = LocalTime.now();
  LocalDateTime dateTime = LocalDateTime.now();
  ```

### 10. **Regular Expressions**

- `Pattern` and `Matcher` classes
- Example:
  ```java
  String text = "hello";
  Pattern pattern = Pattern.compile("h.llo");
  Matcher matcher = pattern.matcher(text);
  boolean matchFound = matcher.find();
  ```

### 11. **Static Fields, Methods, and Classes**

- **Static Fields**: Belong to the class, not instances
  - Example: `static int count;`
  
- **Static Methods**: Can be called without creating an object
  - Example: `public static void showMessage() { ... }`
  
- **Static Classes**: Nested classes declared `static`
