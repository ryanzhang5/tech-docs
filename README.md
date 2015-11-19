 1:in-ivy-how-to-choose-the-latest-version-of-transitive-dependencies
 
 By default, ivy will choose the most recent version, working on the very fair assumption that most libraries are backwardly compatible. If you review the report generated by the report task you'll see the other version(s) marked as "evicted".
 
 http://stackoverflow.com/questions/14238073/in-ivy-how-to-choose-the-latest-version-of-transitive-dependencies


2)http://quartz-scheduler.org/

3)UnsatisfiedLinkError

Thrown if the Java Virtual Machine cannot find an appropriate native-language definition of a method declared native.

4)IncompatibleClassChangeError
The IncompatibleClassChangeError extends the LinkageError, which is related to problems rising from a base class that changes after the compilation of a child class.
http://examples.javacodegeeks.com/java-basics/exceptions/java-lang-incompatibleclasschangeerror-how-to-resolve-incompatible-class-change-error/


5)
	public static void t1() {
		int i = 0;
		i = ++i;
		System.out.println(i); // returns 1

	}

	public static void t2() {
		int i = 0;
		i = i++;
		System.out.println(i); // returns 0
	}
	
	Let's take a close look at what the line "i = i++;" does:

"i++" is evaluated. The value of "i++" is the value of i before the increment happens.
As part of the evaluation of "i++", i is incremented by one. Now i has the value of 1;
The assignment is executed. i is assigned the value of "i++", which is the value of i before the increment - that is, 0.
That is, "i = i++" roughly translates to

int oldValue = i; 
i = i + 1;
i = oldValue; 
With other words, it is a common misconception that the increment is happening last. The increment is executed immediately when the expression gets evaluated, and the value before the increment is remembered for future use inside the same statement.

Solution:

You don't need the assignment at all, just use

i++;
