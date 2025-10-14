Synchronized is a modifier applicable for method and blocks but not for classes and variables.

If multiple threads trying to operate simultaneously on the same java object then there maybe a chance of data inconsistence problem this is called <span style="color:rgb(253, 223, 126)">race condition</span>. We can overcome this problem by using synchronized keyword.

If a method or block declared as synchronized then at a time only one thread is allowed to execute that method or block on the given object so that data inconsistency problem will be resolved.

The main disadvantage of synchronized keyword is it increases waiting time of threads and creates performance problems, hence if there is no specific requirement then it is not recommended to use synchronized keyword.