Here are the most frequently used Set methods in Java, grouped by functionality:
1. Add and Remove Elements
2. Check for Elements
3. Size and Empty Check
4. Iteration and Stream Operations
5. Bulk Operations
6. Convert to Array or Other Collections
7. Compare Sets



*1. Add and Remove Elements*
add(E e)
Adds the specified element to the set if it is not already present.
Example: set.add("Apple");
addAll(Collection<? extends E> c)
Adds all elements from the specified collection to the set.
Example: set.addAll(list);
remove(Object o)
Removes the specified element from the set.
Example: set.remove("Apple");
removeAll(Collection<?> c)
Removes all elements in the specified collection from the set.
Example: set.removeAll(list);
clear()
Removes all elements from the set.
Example: set.clear();

2. Check for Elements
contains(Object o)
Checks if the set contains the specified element.
Example: set.contains("Apple");
containsAll(Collection<?> c)
Checks if the set contains all elements of the specified collection.
Example: set.containsAll(list);

3. Size and Empty Check
size()
Returns the number of elements in the set.
Example: int count = set.size();
isEmpty()
Checks if the set is empty.
Example: boolean empty = set.isEmpty();

4. Iteration and Stream Operations
iterator()
Returns an iterator to traverse the elements in the set.
Example:
java
Copy code
Iterator<String> it = set.iterator();
while (it.hasNext()) {
    System.out.println(it.next());
}
forEach(Consumer<? super E> action)
Performs the given action for each element in the set.
Example: set.forEach(System.out::println);
stream()
Returns a sequential stream of the set's elements.
Example:
java
Copy code
set.stream().filter(e -> e.startsWith("A")).forEach(System.out::println);

5. Bulk Operations
retainAll(Collection<?> c)
Retains only the elements in the set that are also in the specified collection.
Example: set.retainAll(list);
removeAll(Collection<?> c)
Removes all elements in the specified collection from the set.
Example: set.removeAll(list);

6. Convert to Array or Other Collections
toArray()
Converts the set to an array.
Example:
java
Copy code
Object[] array = set.toArray();
toArray(T[] a)
Converts the set to a typed array.
Example:
java
Copy code
String[] array = set.toArray(new String[0]);

7. Compare Sets
equals(Object o)
Checks if this set is equal to another set.
Example: boolean isEqual = set1.equals(set2);
hashCode()
Returns the hash code value for the set.
Example: int hash = set.hashCode();

Mnemonic to Remember Groups:
"Add, Check, Size, Iterate, Bulk, Convert, Compare."

Example Code:
java
Copy code
import java.util.HashSet;
import java.util.Set;

public class SetExample {
    public static void main(String[] args) {
        Set<String> set = new HashSet<>();
        
        // Add elements
        set.add("Apple");
        set.add("Banana");

        // Check elements
        if (set.contains("Apple")) {
            System.out.println("Apple exists in the set.");
        }

        // Iterate
        set.forEach(System.out::println);

        // Remove element
        set.remove("Banana");

        // Convert to array
        String[] array = set.toArray(new String[0]);
    }
}
Using this categorization makes it easier to identify and use Set methods effectively in your projects.
