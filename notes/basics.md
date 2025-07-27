```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, world!");
    }
}
// output: Hello, world
```
## Breakdown of the code:
1. `public class Main`
    is the class name and is always same as the filename (Main.java)

2. ` public static void main(String[] args)`:  these creates a method name `main()`.

    - `public` means the method is accessible from anywhere.  The JVM needs to access it to start your program.
    - `static` Means this method belongs to the class, not to any object. JVM can call main() without creating an object of the class.
   -  `void` means this method returns nothing. It's just meant to run some code, not give back a result.
   - `main` This is the entry point of any Java application. JVM starts from here.
   - `String[] args` means we are accepting string as the arguments in the method. args[0] = "hello", args[1] = "world"

## Data types:

```java
int a = 10;
double pi = 3.14;
boolean isJavaFun = true;
String name = "Saumya";
```

## if, else:
```java
public class Main {
  static int add(int x, int y) {
    return x + y;
  }

  public static void main(String[] args) {
    int nums = add(20, 44);
    System.out.println(nums);
  }
}
```

## array, for and while loops
```java
public class Main {

  public static void main(String[] args) {
    String fruits[] = { "apple", "banana", "mango" };
    System.out.println(fruits); // [Ljava.lang.String;@5a07e868
    // for loop
    for (int i = 0; i < fruits.length; i++) {
      System.out.println(fruits[i]);
    }
    // while loop:
    int a = 1;
    while (a > 0) {
      System.out.println(a);
      a--;
    }
  }
}
```

## Java file structure + import/export 

### 1. **Java = one public class per file**

Example: `Car.java`

```java
public class Car {
    public void drive() {
        System.out.println("Driving...");
    }
}
```

Now to use `Car` somewhere else...

---

### 2. **Importing from another file (same folder)**

Example: `Main.java`

```java
import Car;

public class Main {
    public static void main(String[] args) {
        Car c = new Car();
        c.drive();
    }
}
```

But **this will throw an error**. Why?

Because Java doesn’t allow importing like JS/Python unless it's in a **package**.

---

### 3. **Use directly if in the same package/folder**

If both `Car.java` and `Main.java` are in the same folder, do this:

`Car.java`

```java
public class Car {
    public void drive() {
        System.out.println("Driving...");
    }
}
```

`Main.java`

```java
public class Main {
    public static void main(String[] args) {
        Car c = new Car();
        c.drive();
    }
}
```

Now run:

```bash
javac Car.java Main.java
java Main
```

---

### 4. **Optional: use `package` keyword**

Put this on top of both files:

```java
package vehicles;
```

Then place them inside `vehicles/` folder and compile like:

```bash
javac vehicles/*.java
java vehicles.Main
```




