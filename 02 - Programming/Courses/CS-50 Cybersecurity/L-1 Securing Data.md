## Hashing
```ad-Definition
Hashing is a method by which we convert some plain text and output it as a hashed value that is less readable.
```

* Therefore, a hash function creates a hash value. A password is provided to a hash function and then is outputted as a hashed value.
* With the username and hash values stored in the server, an adversary cannot easily access the accounts on that server.
* When a user now inputs their password to log in, the password is passed to the hash algorithm again and compares the hash value created with the hash value stored.
* Hypothetically, **rainbow tables** are another threat, whereby the adversary has a table of all the potential hashed values in a hash table. This, however, would take terabytes, if not petabytes, of storage capacity to accomplish.

#### Salting

Finally, a problem arises when users utilize the same password and the hashed value of these passwords is exactly the same. How could we solve this problem?

```ad-Definition
Salting is a process by which an added value is “sprinkled” into the hash function, such that a hash value changes.
```

The utilization of a salt value nearly guarantees that the hash values provided by users, even those that have the same passwords, receive a different hashed password.

#### One-Way Hash Functions

_One-way hash functions_ are written in code and take in a string of arbitrary length and output a hash of a fixed length.
Utilizing such a function, the holder of the hash value and hash function will never know the original password. Indeed, in some systems utilizing a one-way hash function, certain passwords may map to the same hash value but it very unlikely.