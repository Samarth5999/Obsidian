If an interface doesn't contain any method and by implementing that interface if our objects will get some ability, such type of interfaces are called <span style="color:rgb(253, 223, 126)">Marker Interfaces</span> or <span style="color:rgb(253, 223, 126)">Ability Interface</span> or <span style="color:rgb(253, 223, 126)">Tag Interface</span>.
For Example: Serializable(I), Cloneable(I), RandomAccess(I), SingleThreadModel(I), etc. These are marked for some ability.

Example-1: By implementing Serializable Interface, our objects can be saved to the file and can travel across network.
Example-2: By implementing Cloneable Interface, our object are in a position to produce exactly duplicate cloned objects.

>[!question] Without having any methods, how the object will get some abilities in Marker Interfaces?
>Internally JVM is responsible to provide required ability. 

>[!question] Why JVM is providing required ability in Marker Interfaces?
>To reduce complexity of programming and to make Java language as simple.

>[!question] Is it possible to create our own Marker Interface?
>Yes but customization of JVM is required (Not in our scope but in my scope :) ).

>[!important] Note
>Marker interface and adapter classes simplifies complexity of programming and these best utilities to the programmer and programmer life will become simple.

