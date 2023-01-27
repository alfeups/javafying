## Reference Equality
**Reference equality occurs when two references point to the same object in the memory.**


## Equality Operator With Primitive Types
We know that the primitive types in Java are simple, non-class raw values. When we use the equality operator with primitive types, we're just comparing their values:

```Java
int a = 10;
int b = 15;
assertFalse(a == b);

int c = 10;
assertTrue(a == c);

int d = a;
assertTrue(a == d);
```

Equality and reference checking work identically for primitives. When we initialize a new primitive with the same value, the check returns true.
Moreover, the operator returns the same result if we reassign the origin value to the new variable and compare it.


```Java
int e = null; // compilation error
assertFalse(a == null); // compilation error
assertFalse(10 == null); // compilation error
```

Java prohibits assigning null to a primitive. In general, **we can't perform any null checks with the equality operator on primitive variables or values.**


## Equality Operator With Object Types
As for object types in Java, **the equality operator performs a referential equality comparison only**, ignoring the object values. Before we implement the tests, let's create a simple custom class:

```Java
public class Person {
    private String name;
    private int age;

    // constructor, getters, setters...
}
```
Now, let's initialize some class objects and inspect the equality operator results:

```Java
Person a = new Person("Bob", 20);
Person b = new Person("Mike", 40);
assertFalse(a == b);

Person c = new Person("Bob", 20);
assertFalse(a == c);

Person d = a;
assertTrue(a == d);
```

The results are quite different than before. The second check returns false while we had got true for the primitives. As we mentioned earlier, the equality operator ignores the internal values of the object when comparing. It only **checks that two variables are referencing the same memory address.**

Unlike primitives, we can use nulls while working with objects:

```Java
assertFalse(a == null);
Person e = null;
assertTrue(e == null);
```

By using the equality operator and comparing null, we check if the object assigned to the variable is already initialized.

## Value Equality
Let's now focus on the value equality test. **Value equality takes place when two separate objects happen to have the same values** or state.

This compares values and is closely related to the Object's equals() method. As before, let's compare its use with primitives and object types, looking at key differences.

## equals() Method With Primitive Types
As we know, primitives are basic types with a single value and don't implement any methods. Therefore, **it's impossible to call the equals() method directly using primitives:**

```java
int a = 10;
assertTrue(a.equals(10)); // compilation error
```
However, **since every primitive has its own wrapper class**, we can use the boxing mechanism to cast it into its object representation. Then, we can easily call the equals() method as if we are using object types:

```java
int a = 10;
Integer b = a;

assertTrue(b.equals(10));
```

## equals() Method With Object Types

Let's go back to our Person class. For the equals() method to work correctly, we need to override the method in the custom class by considering the fields contained in the class:

```java
public class Person {
    // other fields and methods omitted

    @Override
    public boolean equals(Object o) {
        if (this == o) 
            return true;
        if (o == null || getClass() != o.getClass()) 
            return false;
        Person person = (Person) o;
        return age == person.age && Objects.equals(name, person.name);
    }
}
```

First of all, the equals() method returns true if the given value has the same reference, which is checked by the reference operator. If not, we start the equality test.

Further, we test the equality of the Class objects for both values. We return false if they're different. Otherwise, we continue checking for equality. Finally, we return the combined result of comparing each property separately.

Now, let's modify the previous test and check the results:

```java
Person a = new Person("Bob", 20);
Person b = new Person("Mike", 40);
assertFalse(a.equals(b));

Person c = new Person("Bob", 20);
assertTrue(a.equals(c));

Person d = a;
assertTrue(a.equals(d));
```

As we can see, the second check returns true as opposed to the reference equality. Our overridden equals() method compares the internal values of the objects.

***If we don't override the equals() method, the method from the parent class Object is used. Since the Object.equals() method only does reference equality check, the behavior might not be what we'd expect when comparing Person objects.***

While we haven't shown the hashCode() method above, we should note that it's important to override it whenever we override the equals() method to ensure consistency between these methods.

To test for the reference equality, we use the == operator. This operator works slightly differently for primitive values ​​and objects. When we use the equality operator with primitives, it compares values. On the other hand, when we use it with for objects, it checks memory references. By comparing it with a null value, we simply check that the object is initialized in memory.

To perform a value equality test in Java, we use the equals() method inherited from Object. Primitives are simple non-class values, so this method cannot be called without wrapping.

We also need to remember to only call the equals() method on an instantiated object. Otherwise, an exception will be thrown. To prevent this, if we suspect a null value, we should check the value with the == operator.

### Difference between == and .equals() method in Java


<img src="https://github.com/alfeups/javafying/blob/master/img/methodvsoperator.png">


References: 
<li> https://byjus.com/gate/difference-between-operator-and-equals-method-in-java/
<li> https://www.baeldung.com/java-equals-method-operator-difference