We can use transient keyword in <span style="color:rgb(103, 235, 250)">serialization</span> context. transient is the modifier applicable only for variables.
Serialization is the process of converting an object's state into a format that can be stored or transmitted, like a stream of bytes, and then reconstructed later.

At the time of serialization, if we don't want to save the value of a particular variable to meet security constraint then we should declare that variable as transient.
At the time of serialization, JVM ignores original value of transient variable and save default value to the file, hence <span style="color:rgb(250, 169, 157)">transient means not to serialize</span>.
