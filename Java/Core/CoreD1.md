# Collection

## java.util
The Collection interface (java.util.Collection) and Map interface (java.util.Map) are the two main “root” interfaces of Java collection classes.

- List: The List interface in Java provide a way to store the ordered collection.
- Set: The set interface is present is java.util package and extends the Collection interface.
- Map: Key-value collection, Map Interface.  Java Map interface is not a subtype of the Collection interface.

## Iterator
An Iterator is an object that can be used to loop through collections, like ArrayList and HashSet. It is called an "iterator" because "iterating" is the technical term for looping.

## ArrayList
The ArrayList class is a resizable array, which can be found in the java.util package.
- boolean add(E e)
- boolean add(int index, E e)
- E remove(int index)
- boolean remove(Object e)
- E get(int index)
- int size()

## LinkedList
HEAD ──>│ A │ ●─┼──>│ B │ ●─┼──>│ C │ ●─┼──>│ D │   │  
The LinkedList stores its items in "containers." The list has a link to the first container and each container has a link to the next container in the list. To add an element to the list, the element is placed into a new container and that container is linked to one of the other containers in the list.  
Use an **ArrayList** for storing and accessing data, and LinkedList to manipulate data.
![LinkedList](docs/LinkedList.JPG)