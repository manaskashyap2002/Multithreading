### Multithreading

## What is thread?
A thread is a lightweight process that runs independently inside a program.

## What is Multithreading?

Multithreading is the ability of a program to perform more than one task simultaneously using multiple threads.

Real-life example

While using your phone:

One task plays music 🎵

One task downloads a file ⬇️

One task shows notifications 🔔

All happen together → multithreading

## Thread Lifecycle

NEW → Thread created

RUNNABLE → Ready to run

RUNNING → Executing

WAITING → Temporarily paused

BLOCKED → Waiting for lock

TERMINATED → Dead thread


## Important Thread Methods ()
Method  --------------------------------------	Use

start() --------------------------------------	Starts a new thread

run()   --------------------------------------	Contains thread code

sleep(ms)-------------------------------------	Pauses thread

join()	--------------------------------------  Waits for another thread

getName() ------------------------------------	Gets thread name

setName()	------------------------------------  Sets thread name

getPriority()	--------------------------------  Gets priority

setPriority()	--------------------------------  Sets priority

isAlive()	------------------------------------  Checks if thread is running

## How can we create threads in Java?

# By extending Thread class

class hii extends Thread{
	   public void run() {
		  for(int i=0;i<=5;i++)
		  {
			  System.out.println("Hiiii");
			  try {
				  Thread.sleep(1000);  
			  }
			  catch(Exception e) {};
		  }
		  
	   }
}
class hello extends Thread{
	   public void run() {
		   for(int i=0;i<=5;i++)
			  {
			      System.out.println("Hello");
			      try {
					  Thread.sleep(1000);  
				  }
				  catch(Exception e) {};
			  }
	   }
}

public class multithredingUsingExtends {
        public static void main(String[] args) {
        	hii obj1 = new hii();
			hello obj2 = new hello();
			
			obj1.start();
			 try {
				  Thread.sleep(40);  
			  }
			  catch(Exception e) {};
			obj2.start();	
		}
}


# By implementing Runnable interface

package org.kyp.multithreding;


class hi implements Runnable{
	   public void run() {
		  for(int i=0;i<=5;i++)
		  {
			  System.out.println("Hii");
			  try {
				  Thread.sleep(1000);  
			  }
			  catch(Exception e) {};
		  }
		  
	   }
}
class heello implements Runnable{
	   public void run() {
		   for(int i=0;i<=5;i++)
			  {
			      System.out.println("Hello");
			      try {
					  Thread.sleep(1000);  
				  }
				  catch(Exception e) {};
			  }
	   }
}

public class multithredingUsingRunnableInterface {
	 public static void main(String[] args) {
     	Runnable obj1 = new hi();
     	Runnable obj2 = new heello();
			
     	Thread t1 = new Thread(obj1);
     	Thread t2 = new Thread(obj2);
			
     	t1.start();
     	
	    try {
				  Thread.sleep(40);  
			 }
			  catch(Exception e) {};
			  
		t2.start();	
		}     
}


# Using lambda expression 

public class multithredingUsingLabda {
     public static void main(String[] args) {
		Thread t1 = new Thread (()->{
			 for(int i=0;i<=5;i++)
			  {
				  System.out.println("Hii");
				  try {
					  Thread.sleep(1000);  
				  }
				  catch(Exception e) {};
			  }
		});
		
		
		Thread t2 = new Thread (()->{
			 for(int i=0;i<=5;i++)
			  {
				  System.out.println("helllo");
				  try {
					  Thread.sleep(1000);  
				  }
				  catch(Exception e) {};
			  }
		});
		
		t1.start();
		 try {
			  Thread.sleep(40);  
		  }
		  catch(Exception e) {};
		t2.start();
	}
}



--------------------------------------------------------------------------------------------
## Methods is Multithreading

# join() 

The join() method makes one thread wait until another thread finishes execution.

thread.join();

Key Points (join())

join() pauses current thread

Used for thread synchronization

Throws InterruptedException

Commonly used in main thread

# isAlive()

The isAlive() method checks whether a thread is still running.

thread.isAlive();

key Points (isAlive())

Returns true → thread is running

Returns false → thread not started or finished

Used to check thread state

Does not stop the thread

## setName() and getName() Methods in Thread

These methods are used to assign a name to a thread and retrieve the thread name.

## setPriority() and getPriority() Methods in Thread

These methods are used to set and get the priority of a thread.
Thread priority helps the scheduler decide execution order.

# Thread Priority Range

MIN_PRIORITY  = 1

NORM_PRIORITY = 5   (Default)

MAX_PRIORITY  = 10


#  Synchronized

The synchronized keyword in Java ensures that only one thread can access a shared resource at a time, preventing data inconsistency.
