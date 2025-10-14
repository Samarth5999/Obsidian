Outside person can't access our internal data directly or our internal data should not go out directly. This OOP feature is nothing but <span style="color:rgb(253, 223, 126)">Data Hiding</span>.
After validation or authentication, outside person can access our internal data.

Example-1: After providing proper username and password we can able to access our Gmail inbox information.
Example-2: Even though we are valid customer of the bank, we can able to access our account information and we can't access other's account information.

By declaring data member(variable) as `private` we can achieve data hiding.
```java
public class Account
{
	private double balance;
	.
	.
	.
	public double getBalance()
	{
		// validation
		return balance;
	}
}
```
It is highly recommended to declare data member(variable) as `private`.

**The main advantage of data hiding is Security.**
