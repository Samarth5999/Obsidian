volatile is a modifier applicable only for variables and we can't apply anywhere else.

If a value of a variable keep on changing by multiple threads then there may be a chance data inconsistency problem, we can solve this problem by using volatile modifier.
If a variable declared as volatile then for every thread JVM will create a separate local copy. Every modification performed by the thread will takes place in local copy so that there is no effect on remaining threads.

The main advantage volatile keyword is we can overcome data inconsistency problem but the main disadvantage of volatile keyword is creating and maintaining a separate copy for every thread increases complexity of programming and creates performance problems, hence if there is no specific requirement it is never recommended to use volatile keyword and it is almost deprecated keyword.

final variables means the value never changes whereas volatile variable means the value keep on changing, hence volatile final is illegal combination for variables.
