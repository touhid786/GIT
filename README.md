Java from Basics to Advanced
Lecture thumbnail
6:26 / 1:08:17
Transcript
Hey guys.

Welcome to Concept and Coding.

And this is Shreyansh.

And today we are going to do the multithreading part two.

So here in this case today we will cover this this topic creation of thread and also synchronization

and inter thread communication.

So this two topics we will cover today right.

Okay, let's just start without wasting any time.

So what are the different ways to create a thread?

So there are two ways to create a thread.

One is using an interface runnable interface and another is extending a thread class.

Right.

So here the first question at this point of time should come to your mind that hey, why we have two

different ways of creation of thread, right?

I'll tell you now that.

Why.

So one is through interface, another is through extending the class.

Why you remember.

Just remember that one scenario in Java, if you have class A, you can extend it from its parent class

and you can have only one extend.

You can have only one parent.

You cannot have multiple parent.

But if you have class A you can implement multiple interface interface one comma.

Interface two.

Comma interface three.

Right.

So Java has provided us both the options that hey, if you have any class which you have already extended

from somewhere like you or you have already extended from parent class.

But you wanted the thread capability for this class.

Yes, you again can do by implementing a runnable interface, right?

Even though you have already extended because in Java you can only extend from one parent class, you

cannot have extend some parent one and also the thread class no two extend.

We can't do so multi but.

Interface you can have multiple.

Right.

So Java has provided us both the ways.

So that's why we have two ways through interface and through extend.

Let's see that.

So this is the current.

Glass architecture we have here if you see that runnable.

So let's see the code here.

The runnable.

So runnable is a functional interface which has one abstract method run.

So here this is a.

Functional interface, which has this abstract method right?

But here, if you see that this is not a thread, this is not a part of thread.

This is just a normal functional interface.

Then this is the thread class.

The thread class here.

If you see this.

This thread class.

Is actually implements runnable.

So thread class is actually implements the runnable.

And it has all the method which takes care of creation of thread, stopping of the thread, interruption

of the thread, making thread sleep, everything right.

And it also implement this run method because this is an abstract and this is a concrete class.

So it has to implement this run method.

But this is actually a thread class which takes care of the total life cycle of a thread.

Right.

Okay.

Now let's see that.

So but this is how currently exist.

And then we will see that how to create a runnable interface and how to create a thread class directly

extending from a thread class.

Let's say that first implementing runnable interface.

So this is we already have this is we already have Java provide.

This is that we have one functional interface.

And thread class implements this.

Now we want is that uh we want to create another class which, which should have some tasks which need

to be performed by thread.

So what I've done is we can create one class here.

Which implements this runnable also write this is class.

My class, let's say implements the runnable and this run is the method which has to provide the implementation.

So whatever you implement in here.

Actually.

Thread will invoke it.

Thread will invoke it.

How?

I will tell you, but thread will ultimately invoke this method.

Run.

How?

How I will tell you.

But remember that this is not a thread again.

This is not a thread.

This is the thread class.

This is a thread class.

This is just a normal class which implements the runnable interface and provide the implementation of

this run method.

Right now.

How the thread will invoke this run method we will see.

So step one is create a runnable object like this.

Create a class.

So create a class that implements the runnable interface.

So here I have created a class multithreading learning implements runnable.

So here I have taken my class right.

So now let's say if I am creating one class.

Multithreading learning right and implements this runnable and provided an implementation of this run

method.

So run method I have provided this implementation.

For example, I have just say that System.out.println.

Code executed by thread the thread name right.

Now, what is the, uh, yeah, implement the run method.

So I have already implemented the run method here.

So this first part is done.

I have created this.

Now how to invoke a thread to call this run method.

Step two create an instance of the class that implements runnable.

So first we have to create an object of this class which we have created multi-threading learning.

Right?

So here I am creating the object of this multithreading running runnable object.

This I have provided an object.

Then what I have done is pass the runnable object to the thread constructor.

I am now creating the thread so this is where thread is created.

I told you that thread is the class which actually creates the thread, so I am.

So this constructor thread constructor will actually construct the thread.

And here in that I pass this runnable object.

So here if you see that this is the thread class.

So this should have one constructor which passed.

So which takes the runnable object.

So here.

Takes the runnable object.

Because thread is also a child of runnable, it also has implemented the run method.

So now let's see how it will help.

So what I have done is here.

Thread creation is done, thread is constructed and it knows that okay this is the runnable object which

is passed to me.

What is the runnable object.

Multithreaded running.

So this multithreaded learning object is passed to this thread.

Now we have to start the thread.

So at this point of time only thread is created, not started.

Now we have to start the thread.

So we have.

We are now starting the thread thread dot start method.

And when we invoke the start method internally, it calls the run method right?

So we are calling this a start method on what object.

Thread right this thread.

So this start internally called run.

So what.

Which method it will invoke run off thread only.

So it will invoke this inside this thread.

This run method will get invoked.

So we'll see that run.

So this run method will get invoked.

Now see this?

What this run method is doing.

This run method is doing.

If target not equals to null, invoke the target dot run.

Now you can you guess what is this target is.

Right.

So here if you see that.

When we created the thread.

What runnable object we pass.

Okay, this is the multithreaded running runnable object we pass.

So here if you see that target is nothing but a runnable object.

So whenever we constructed a thread, whenever we constructed a thread and we have passed the runnable

object to it.

This runnable target is will be set as not equal to null and the reference will be set to this one.

Whatever we will pass to it right and inside the run method.

Inside the run method.

If it is not equals to null, it will call target dot run.

So ultimately this runnable object dot run will get invoked.

So ultimately this will get invoked by this thread.

You got it.

So this when we say that this is the method which actually invoked by thread.

How so we first create a thread and we pass this.

Runnable object to it, and in the run method we will see that hey, if runnable is not equals to null,

then invoke the runnable dot run.

So whatever the object.

So let's say if you have 1010 runnable objects, write runnable one, runnable two, runnable three.

So while creation of the thread constructor, if you have passed runnable three reference, then inside

a run when it calls when it invokes the run method of this runnable.

So this will get invoked.

Right.

So here, if you see this is how with the interface the thread can be constructed.

So here.

Then if you see this example.

Now what I have done is where if you run this what how it will run.

Let's little bit clean this up so that uh, we can see its execution also.

So now when you executed this main method.

So first by default what what thread will construct it is main right or main thread with the name main.

So going inside main method what is the thread main then what I'm done is I'm creating a runnable object.

Pass it to the thread right and starting the thread right.

Then it started the thread and this main.

So here it will create some new thread and.

But the main is continue.

So finish main method main is finished.

But one new thread has been created.

Have I started it and in when I call the start method internally will call run and inside the run.

We have checked that if runnable object is present, it will call the run method of that.

So it will call this run object code executed by thread thread name.

Code executed by thread thread name.

Some new thread has been created and that executed this run method.

So you got it.

How to create an object.

Create a thread using runnable interface.

And if you see that this provide a lot of capability that in this runnable interface, this is one thread

class.

Now we can have you can have any number of classes, let's say class one, class two, class three.

And this class can even child of some other class let's say this is implements.

This is implement.

This is implement but this class extend from this.

Right.

So here, if you see that what I'm trying to say that these are not thread classes, they can do lot

of other tasks, but yet they can use the, uh, we can invoke the thread on this method because inside

this thread.

We are passing this runnable object, whatever the runnable object we are constructing while creating

a thread, we pass it and that it will invoke the run on that one.

Right.

So these classes are not thread.

They can do a lot of other tasks.

They can implement some other interface.

Also they can extend one another class.

They have some other method also.

So they can do a lot of stuffs.

Yet taking the capability of threading we can invoke thread on this method.

Okay.

So in mostly live and production, you can say that in company standard.

Generally this method is used, but it's good practice to know the another second approach of creating

a thread using extending.

So this is we already have.

So we have a functional interface.

So we have a functional interface.

And this is the thread class.

Now we are extending.

From this thread class.

So now this is also a thread class.

This is a thread.

This is you can say that the subclass.

Subclass.

Or you can say that a thread subclass.

So.

But this is also considered as a thread.

Right because it is directly extending from the thread.

So whatever.

The thread has the capability.

This class also has the same capability.

So it because it is extending from it now.

It cannot extend from any other class.

Right.

Now let's see how to create.

So first create a class that extend the this one and override the run method to tell the task which

thread has to do.

So I am creating one class multithreading learning.

So I am creating one class let's say multithreading learning.

Extend the thread.

So extend the thread.

And provided the run method what I have to execute in it.

Second, we have to create an instance.

Right.

So here now if you see that.

How to create it.

So I have created now this object of this new class which I have created.

I have to create an object of this class.

So what?

The name of, uh, my class.

What is the name I have given?

Multi-threading learning.

So this is like multi-threading learning.

Multi-threading learning.

So now we have to create an object of this class.

So we have created an object of this class.

Now you see that I don't need to create a thread object now because why.

This is also a thread only.

This is a direct child of thread.

It has all the capabilities which are already present into the parent.

This.

My class has all the capabilities which are present into the thread, right?

So you don't have to create a thread class and pass this object to it.

No necessary because this is itself is a thread class.

Right.

So here what I have done is I have created the object of.

This new class, which is a child of thread.

Now, since it's a child of thread, it has all this method supported so I can even so this all methods

have been can be accessed from the child class.

So I can call a start method directly from here.

So I can call a start method.

So now when this start method is called.

Now when a start method is called internally it will call run method now.

So I on which object I have called the run method.

This multithreading learning.

This one multithreading learning.

So which run it will invoke this one the Overrided one.

Right.

If you don't provide this Overrided one right, it will go to its parent and call its run method.

So here if you see generally in the parent thread class, in the thread class, run only for runnable,

we are invoking it.

But rest we are doing nothing.

So here it also says that if the thread was constructed using a runnable, then runnable object run

method is called.

Otherwise this method does nothing and return.

So that's why generally we do override.

So that's why whenever you create a child thread.

Directly extending.

We have to generally override it because in the parent thread run class it will perform nothing.

Right.

So we have to provide what whatever the new thread you are constructing, what it has to do.

But actually you got it right.

We can create a child class, whatever the child class you have created for the thread and directly

call the start method, it will internally call the run method and this will invoke this.

So now let's see.

So going inside the main method when you run this.

So it will print thread dot current thread get name main.

So it created a thread here.

So thread creation has been done, but it's not yet started.

At this point it is started and finished.

Main method.

The main thread has been completed.

But the new thread is yet to work, so it will call run method and it will call multithreading learning

run method code executed by thread some new thread, right?

Exact same functionality.

So you got it right.

What are the two different ways of thread creation?

Why?

There are two different ways.

Right and in industry mostly, which one is preferred because it provides us a lot of capability?

A class can.

Have a lot of composition, right?

You can implement so many interfaces you can have even extend from other class also.

So.

That's why this is generally approach is not used in the industry standard.

But the two ways is created, right?

Why?

We have two ways to create that very important interview question.

I think now you should get it.

I have explained this part.

Since now we know that.

How to create a thread.

Now let's understand the thread lifecycle.

Let's see this diagram well.

Okay.

So whenever we created the thread thread object equals to new thread.

Whenever we did this at that time a thread is created.

Whenever we created, a thread is created and it is in new state.

You can say that thread is created but it is not yet started.

When you call that thread dot start.

When you call thread dot start, it goes into the runnable state.

So it goes into the runnable state.

So this is your runnable state right.

So here if you see that in the runnable state right.

Runnable state.

I have provided this to one is runnable.

And another is running.

So generally, if you see that there is this running is not in state only everywhere you will see,

you will see runnable only run running is not a state.

This two are taken as a together.

So what happens is they keep on switching between it.

So runnable means that it is waiting for the CPU time.

As soon as CPU will give it a time, it will.

Move to the running state.

As soon as contact switching happened, it will again go back into the queue and wait for the CPU time.

It goes into the runnable so it keep on based on the context switching.

It keeps on into runnable or running.

But generally we call that runnable state means they are running.

Right, but runnable running is like runnable is waiting for CPU running is got the CPU time, but generally

you can say that they are in runnable state when we say that runnable state.

So whenever you call start it goes into the runnable state.

Right.

Difference between runnable running I told you waiting for the CPU got CPU, but generally this this

rectangle, which I have shown is considered as one runnable itself.

Running is generally a you can say a part of it.

So yeah.

So when you call this thing, it goes into the runnable state and when it's completed its task, it

will.

Finishes execution and this thread gets finished terminated.

Once the thread is terminated, there is no way it will go back to the runnable.

It's terminated.

So this is one flow.

From new.

It goes to runnable, and from runnable it finishes execution and get terminated.

But while it is in runnable runnable, it is possible that.

It can goes into a block state.

So let's say there is certain IO tasks like input output operation task.

So let's say this like reading from a file or database.

So now let's say you want to while you are performing the thread work it has to read some data from

a DB.

It's an IO task right.

So that time it is waiting thread is waiting to get the data from the DB.

So what it for the CPU?

It is now in a blocked state.

This thread is in blocked state.

Right.

Once the I o operation task is done, it goes back to a runnable state.

Right.

It goes back to runnable state.

Also, one more is whenever, let's say thread wants to acquire a lock on a particular resource.

And let's say some of that resource is already locked by some other thread.

Then also it has to wait, right?

So it might go into blocked state.

And once it get the, uh, lock on that particular resource, it come back into the runnable state.

Right.

And as soon as CPU will get the time, it will start running.

Another is waiting, so we can explicitly call the wait method and make the thread wait.

Or you can say that make the thread block.

So this is like internally while running it, wait for some operation to perform like DB read, acquire

lock.

And this is like we call the wait method explicitly and make it to a wait state and it will be in wait

state continuously until we don't call the notify method.

Notify means hey, come back into the runnable state.

But if you if you don't invoke the notify method, it will.

This thread will be keep waiting okay, that's the difference between blocked and waiting.

Another is thread time waiting like sleep method inside a sleep you can give a time hey for ten second

go and wait as soon as that ten second finish.

Automatically it will goes to a runnable state back.

Okay.

So that's where it is known as timed weighting.

So after a particular time automatically it goes to the runnable state.

And only for that time it will.

It is waiting.

Now at all this point, we can stop the thread and we can terminate it so it can be terminated.

Right at at any point of time.

Even the thread is just created, we can stop it.

We can stop it, right?

So you got it right.

The life cycle of a thread.

So we can create it.

It goes to the runnable state from runnable.

It can either go into blocked state.

Maybe it requires some DB operation.

Acquire log.

It has to wait.

And after once it got that it resumed the processing goes into the runnable state.

Or we explicitly, uh, make the thread wait and it goes into the runnable only when we call this method.

And there is something called time waiting, like sleep, uh, for some time, or it is waiting for

some other thread to complete.

Right?

And once the other thread will complete, it will then goes back to the runnable state.

Okay.

So we will go this check this method in uh with an implementation we will get more clarity.

But this is generally the thread lifecycle.

These are the different states.

So first state is new.

Thread has been created but not yet started.

It is just an object in memory.

Second is runnable thread is ready to run, waiting for the CPU time.

Running is when thread start executing its code.

See it got the CPU time and this is generally a one state only runnable.

Identified with the name runnable.

Blocked block means whenever thread goes into the blocking state, like IO read reading from a file

database or lock acquired it.

And if thread wants to lock on a resource which is locked by other thread, it has to wait.

Now one thing you will see that something called monitor locks.

Whenever the thread goes into the blocked state, it releases all the monitor lock.

Keep that in your mind for the time being.

I will come to this monitor lock very soon, but remember that whenever the thread is blocked, it release

all the monitor locks.

Waiting thread goes into this state when we call the wait method and its make it non runnable.

It goes back to runnable when we call notify or notify all method.

And also it releases all the monitor logs at this state.

Also, it releases all the monitor logs.

Time weighting thread weight for a specific period of time and come back to reasonable state after specific

condition met like sleep it do not release any monitor lock during time weighting it do not release

any monitor lock right.

Terminated life of a thread is completed.

It cannot be started back again.

Right.

So these are the states of the thread.

And one thing which is pending is what is monitor log like this release.

The monitor lock.

This also released the.

Monitor log.

This do not release any monitor log.

And at this point of time when it is runnable, it put the monitor log actually.

So now let's before I tell you an example right of this all this method.

Weight.

Sleep.

Run.

Start.

Let's first understand the monitor lock.

Okay.

Uh, what does monitor Log will do?

It helps to make sure that only one thread goes inside a particular section of code.

Generally, you can say that a synchronized block or method.

So you know right.

Whenever we have put synchronized on a method let's say this is my method void.

Uh, let's say uh let's say synchronize I have put and.

This is my method.

Method.

So we know that if multiple threads are coming to this thread one thread, two, only one thread will

go at a time.

How?

Because this synchronized will put a lock.

So where on which it is putting a lock.

So whichever is calling this method.

So let's say this is class A and this method is present inside class A.

Now if other class is first creating an object of class A, class A object equals to.

New class A.

Now this object dot this method one let's say.

Method one.

Now it is calling this method.

So let's say this is thread one.

This is calling this method.

Then also thread two.

It is using the same object.

It is using the same object and calling this method one.

Like.

Remember both the thread is using the same resource.

Both the thread is using the same resource.

So thread one and thread two, both using this same object and calling the method one.

Now two threads are coming to operate on this method.

Now this method is synchronized.

Now what this synchronize will do.

It will put a monitor lock on this object.

Right.

It will put a monitor lock on this object, so only one will get a lock and it will perform a task.

Now other will wait to acquire that monitor lock.

Now one will finish this synchronized block or method.

That monitor lock will be released.

And now other will get and perform the task.

Right if they both this thread one and thread two works on different objects.

So now it is creating different object.

Object two this is object one.

This is object two new class A.

Now it is calling object to dot method one.

So now here if you see that math thread one is invoking with object one of this class, and thread two

is invoking with the object two different object of this class.

Now monitor so they can both go inside because.

So each object has the monitor lock.

Right.

So.

During synchronize thread one, it will put monitor lock on object one right, and no other thread can

get an monitor lock on the object one while T1 has already logged it.

But T2 is working on object two, so it has its own monitor log, so it will when T2 goes inside, it

will put this monitor lock.

So you got it.

Each object has monitor log.

Now let's see an example.

We will see an example and see that let's first uh see this screenshots.

Then we will implement it also.

So I have created one class monitor lock example.

Here.

Task one is one method which is synchronized.

Right.

This is synchronized method.

It is doing nothing.

It just inside task one and I'm making it sleep for 10s right thread dot sleep I kept it.

Whatever the thread is going inside, I kept it sleep for 10s.

Now I have another method.

Task two.

But here, if you see that I haven't put synchronize on the method level, I have used a block.

So first I have print before synchronized and then I am putting a block.

Synchronized block and use this I will tell you how why this inside synchronized.

And then the task three.

There is no synchronized neither block neither this method.

So three.

Simple method.

Task one.

Task two.

Task three.

They are just printing.

System.out.println.

Now here.

If you see that I am creating a one main method.

I am creating this object.

So I have created one object.

Now see that I am creating three threads, all working on the same object.

Same object.

Right?

I told you that.

Every object has monitor law.

Right.

So now I have created only one object.

Now all three threads has to work on this object.

So I am creating.

So I told you right how to create a thread.

So I am using this lambda expression.

I told you right in the start.

This runnable is an functional interface.

It has one abstract method.

So you know that for the functional interface we can create a lambda expression.

So either you have to write this class implements runnable and provide this run and provide this.

Or I can even directly uh do like this.

New.

Thread new thread and use the lambda expression here itself and provide the implementation this part.

Right.

I hope you have understood the functional interface lambda expression well.

So I think this would be easy to understand.

So I'm creating let's say thread one new thread and I am passing the runnable.

Runnable is the functional interface.

And it has only one method run which do not accept any parameter.

Right.

So I passed it right.

And I am telling that hey, whatever the run method it will invoke, it will have to this perform this

task in the run method.

So it would be equivalent to run and inside run it has to do object one dot task one.

So object this is the object.

It has to do call the task one.

So it has put call the task one.

Thread two is creating a new thread.

And it invoking the same object, but task two it is invoking this task two.

So thread two needs to invoke this thread one need to invoke this.

And I have created a thread three new thread and.

Its run method will do this.

Invoke the task three.

So this is the thread three.

It will invoke the task three.

And I have started the three thread.

So this is thread creation.

Now I have to start it.

So when I started thread one dot start.

So thread one will start will invoke its run method.

So ultimately this runnable run method will call it will call object dot task one.

So object object this object task one.

So this is synchronized.

What it will do is on this object it will put a lock.

Monitor log by.

Thread one.

Monitor log by thread one on this object.

OBJ.

Okay.

Now thread two dot start.

And it goes inside.

Task one and it.

Now it is waiting.

Right.

It is not yet completed.

I, uh, explicitly put the time second that.

Okay, it takes some time to complete this.

Now thread two dot start.

So thread two will ultimately call this task two.

Now inside this task two it goes.

It will print task two.

But before synchronize it will print it.

Now it also want a lock.

And I have put this.

So this is like this object which on which I have invoked this task two.

So the same object.

The same object.

The same object.

It now it want to monitor log which is already acquired by thread one.

So now it will wait.

Thread two will wait.

So now you understand what I'm trying to say.

That monitor log will help you to make sure that only one thread will go inside a critical section,

no matter if it is a different method itself.

Each object has monitor log.

If somebody has put a lock on it, right.

And if another thread want a lock, put a monitor log that has to be released by the previous thread

no matter which.

So during synchronize it try to put a monitor lock.

So now at this point it want to put a monitor lock on this.

This is the object reference.

It is the same and it is put by thread one.

So it will wait.

Thread two will wait to complete it.

So thread three dot start.

So it will invoke task three.

So it will go inside.

This here is no synchronized.

No need to put any lock so it will print it.

Now, after 10s thread, one will complete its task and then it will release its lock.

Then it will go inside and print it inside, synchronize and then it will.

Complete.

Okay.

So here let's see the implementation part.

Let me show you.

So this is the monitor lock example.

Right.

This is the monitor log example.

So here I have task one inside task one.

I make the threat.

Sleep for 10s.

Task one completed.

Task two before synchronize.

I am putting a lock here.

Inside.

Synchronize and completed task three.

No.

Synchronize.

Uh, monitor lock.

Main method.

So here what I'm doing is I am creating one thread.

Right.

I am creating one thread and I'm passing.

So here you got it right.

Either you can do this.

So let me show you what is if I don't use lambda, what should be the way?

So let's say I am creating, uh, monitor thread one.

Right.

I have to implement runnable, right?

And if I implemented it, I have to implement its run method.

Right.

And uh, so here.

Object one this object it has to work on, right?

So in the thread one I have to have this object.

Monitor.

Example object.

Right and have let's say monitor thread one constructor, and I will use this constructor to set this

object.

This dot obj equals to obj.

So I will set this and inside the run method what I am doing.

Object dot task one.

So calling the object dot task one write either.

One way is that I have created this class like this.

Or using Lambda.

I can directly do like this.

So, uh, for thread two and thread three, let me do lambda one and thread one.

Let me first create a monitor thread one or instead of this monitor thread one, let me say that it

is a runnable class monitor thread one runnable.

It will clarify, right?

It's a runnable class.

Uh, runnable obj equals to new runnable and pass this object so that they all work on the same object.

And instead of this now lambda I will pass this runnable object okay.

So either way is that I do this.

For this I need to create this class or another with the lambda.

Short form is like directly do this.

The lambda will take care of doing that.

I think you already know.

So yeah, I have created one thread.

One thread.

One will work on, uh.

The stars one and inside the task one.

I have put this one.

So now let's see the.

Now let's run it.

So here inside task one.

Task three is completed.

Task two before synchronize.

But see not yet finished.

It is waiting for thread one to complete.

Task one to complete.

Task one completed after ten second.

Then task two goes inside.

You got it right.

What happened here?

Right.

Because thread one when it goes, when it starts, thread one, thread one.

Call the task one.

This synchronized bottom monitor.

Lock on which object?

This object.

Right.

It put a monitor lock on this object and it goes inside.

Task one.

It put inside task one and it goes into the sleep.

Now it is sleeping right now.

Thread two start working.

So it calls the task two.

Task two.

But before synchronize it, print that.

Now it also wanted a lock on this object.

So what is the object?

This.

And they both are thread one and thread two.

Both are working on the same object and thread one already has the monitor lock.

So it has to wait.

It has to wait.

So thread two didn't get the lock.

So this task two inside a synchronize.

It didn't print it right.

So it is waiting.

Now thread is uh thread three start.

So thread three printed task three.

So it is done completed.

Now after 10s thread one completed its task, it made the task, one completed it goes out of the synchronized

block.

Monitor lock is released on this object.

On this, uh, object.

And then thread two got the to, uh, lock now and work.

Okay.

So what I, I think monitor log should be very clear.

It helps to make sure that only one thread goes inside a particular section of a code a synchronized

block, no matter different method or not.

Every object has monitor log.

Right.

So it is if you are putting a lock.

On the same object.

Then only it makes sense, right?

If two threads are working on a shared resource.

Right then only it makes sense.

But if you have different object.

Object one.

Object two.

Right?

Then it is not a shared resource.

Why?

I'm telling you monitor log this because that is very important when we will see the real example now.

Now let's see that if you understand the monitor, log properly.

Now let's see this.

Whatever the methods we have encountered.

Right.

Start.

Run.

Let's see that now.

See it's example.

Okay.

Let's first see this screenshot.

Let's first understand what I am doing it.

Then we will code it also where it will get super clear.

So what I am doing here is.

I am first creating a shared resource class.

Shared resource class.

So what the shared resource is, is it has a boolean item available.

Right item available is currently false.

Item is not available.

It has two methods.

Add item.

Consume item.

Whenever the ad item is method is called, item available is marked as true and it calls a notify all.

I'll tell you what is the usage of notify all consume method.

Whenever consume is method is called it make item available false right?

It makes uh item available false.

And if item is not available, it has to wait.

I'll tell you how it is working.

So just understand that shared resource has something item available.

It has two method add item consume item add item makes item available to consume item makes item available

false.

Now I have to create two.

Two tasks.

Produce task implements.

Runnable.

And consume tasks implements also runnable I can I don't need to create this class.

I can directly do it through uh lambda, but for better clarity, let's add it.

So okay, so produce tasks.

So what I am doing is produce tasks is working on the shared resource.

So during its constructor produce task this shared resource will get set.

Now inside this run method.

What this producer producer threat has to do because some thread has to invoke this method, right?

Some thread will invoke.

So I'm just printing which thread is this thread name producer thread.

Now I'm waiting it.

Now I am waiting it like thread dot sleep.

I'm making it.

Wait, I'll tell you why.

So after five seconds it will go and add an item.

That's the produce task is doing.

So what I'm doing is I'm making the thread to sleep for five seconds and then I'm adding it.

Consume task.

What it is doing is it is using the shared resource.

Whatever the reference, I will pass it will set it and inside its run method I'm just printing what

is the name of the consumer thread and directly.

No waiting it, just try to consume it.

Now this is the main method.

So here System.out.println.

Main method.

Start.

Okay, I have created one shared resource.

I have created one shared resource object.

Right?

Now I have created one producer thread new thread and pass the runnable object new produce task runnable

object and this runnable object produced us.

I have assigned this shared resource object to produce task.

Now I created the consumer thread and in the consumer thread.

Also I passes this consumer task runnable class object and also the same object reference I passed.

So now the both producer and consumer are working on the same same shared resource same object.

So at this point of time your thread is in new state.

Thread is created but not started.

Right.

And I told you right?

I don't need to create this class.

Also, I can directly do it using lambda.

So for consumer thread I can do new thread right.

And whatever I am doing here consumer thread and consume task I can do like this.

Also no need of creating this class, but I'm just saying it's an alternative.

You can even write it for more clarity.

Just.

But I can do like this way also or.

But now, let's say now your thread is in new state.

I have created two threads producer thread, consumer thread, producer thread.

Is this runnable?

Task I have provided consumer thread.

This runnable task I have provided and thus they are working on the same resource and they are invoking

the on the same resource.

They are working on it something there it is resp produce task is adding the item.

Consumer task is consuming the item.

Now I am starting the thread, so now it is in runnable state.

Your thread is in runnable state now.

Producer thread dot start.

Consumer thread dot start.

Now let's say both the thread started.

So when the thread is started it will call the run method internally.

So for producer thread what is the runnable.

Object produced tasks, so it will invoke its run method.

So what?

It will print it.

It will print producer thread some thread name.

Now it is waiting.

So producer thread is waiting.

Now.

It's not doing anything.

So it is waiting here.

Sleeping.

It is sleeping.

Let's say currently it is sleeping.

While consumer thread is also initiated, so it will call its run method.

Consumer thread is working on this runnable consumer task, so it will call its run.

Consumer thread invoked.

What is the thread name and it try to consume on this shared resource consume task while it is sleeping.

It call the consume task so shared resource this class consume item.

Now it is trying to call this consume item.

So this is synchronized so means.

On this object.

Shared resource object.

Right.

There is a, uh, monitor lock now.

By what?

By consumer thread.

Right.

It put a monitor lock by consumer thread.

So consumer consume item method involves just printing.

Like now it checks hey item available.

By default item is false, item is not available.

So when item is not available, what I did is I make it wait I.

Explicitly call the weight method.

I told you whenever it call a weight method.

Now thread will go into non runnable state right?

And it releases all the monitor lock.

So now when it is waiting it will release this monitor lock also.

So there is no lock now.

And it is waiting right.

Now somebody has to invoke the notify to make it again.

Goes into the runnable state.

Now it is waiting.

Okay.

So now let's say five second is completed for the producer task.

And now it invokes, uh, from sleeping.

It's a timed waiting.

So it's a timed waiting state.

So now it is completed five second it proceed further and it add the item so it goes into the add item.

It is a synchronized.

So it is a same object.

Now it will put a monitor lock.

By.

Produce task.

It will put a monitor log on this object.

Now what will make this item available?

True item is now available and now it will call notify all.

Hey, all the threads which are waiting for this object which are waiting on this object you guys invoke.

So here this thread is waiting.

Right?

The consumer thread was waiting.

Write on this object.

Same object.

So this this will get now because of this, notify this.

Get back to the runnable state.

Right.

And it completed its task.

So this monitor lock is also released by producer.

Uh, this produce.

So and it completed its task.

Now this from this weight the consumer the consumer task against.

Check the item available.

Yes.

Now item available because producer has added the item.

True.

Now it not wait.

It goes out of this and it will print item consumer.

And now it will make it false and it goes out.

Right.

And it will release its, uh, lock now and it goes out.

Okay.

So this is the implementation right.

And here we can check it.

So we can even write this if you want.

Uh but here you can see that this is the shared resource.

This is the shared resource item available currently.

It is false in add item which is a synchronized.

It is uh making it true and notify like whoever is waiting on this object will wake up consume item.

It is also synchronized.

An item is not available when item is not available.

Right it is.

Keep the thread into wait state.

Otherwise, as soon as it is available, somebody call the notify.

It will go and consume it.

Now here, if you ask that why we have while loop.

Why can't we have if condition here if condition is also true.

But if you read the Oracle documentation right.

They tell that sometimes superiors wake up can happen a thread which is waiting sometime because of

some, uh, system noise or something.

They got wake up even though somebody has invoked notify, they got wake up.

So it's always good to check again that hey, whatever you are waiting for, is it fulfilled or not?

Then start the working.

Okay, so that's why it is better to check on while loop.

That's why it is known as a superior wakeup to avoid the like superior wakeup.

That's why I checked on while loop.

And if it is available, it goes out and it make item available.

False.

Right.

So producer tasks.

Let's implement this.

Right.

Let's implement this.

Okay, let's code it.

Uh, so let me first delete everything.

Delete.

Okay.

Now let's do this with.

So I am, uh, building one shared resource class.

So the shared resource costs I am putting.

Is item present?

Currently it is false.

Right.

And I am putting one method add item.

And whenever the add item is called is I am making it true and I am making one like consume item.

And whenever this is consumed I am making is item present equals to false again.

Right.

So this is the basic shared source.

Right.

And.

Also I want to create the threads.

I will add, synchronize and all.

But first let me add a main class.

So inside the main class.

So I am not creating those runnable interface.

I am using the lambda.

So I am creating thread and uh, so let's say I will give it a producer thread.

Producer thread.

New thread.

I am using a lambda expression.

To implement the run method and in the producer thread what producer thread has to do.

First I have to create an object of this shared resource.

Shared resource object equals to new shared resource.

Okay, so producer thread has to invoke the add item on this right?

It has to invoke the add item on it and uh consume thread.

Creating a new thread.

It has to do consume item on it.

But now we have to.

Since both the threads are working on a same shared resource, we have to use synchronization to avoid

the conflict.

So I am also synchronizing this.

So this synchronize will put a lock like on whichever object they invoke.

So now let's say if somebody is trying to consume it.

Right.

So it will check if.

Is item present false.

If it is false, it becomes true, then I.

That thread has to wait.

Right.

So I have to put into a try catch block.

Some exception handling goes here.

And instead of this if let me do while loop to avoid, but at least in testing I can use if but you

know right why we keep while loop to avoid any spurious wakeup somebody if else can wake up but generally

if is okay for that okay so if item is not present it will wait.

Else it will is present okay.

So.

That is done and I will put some.

Law logs also let system.

Dot out dot println.

Thread.

Let's say consumer thread inside.

Consume item method.

Right.

It is inside this.

And let's say I will put it here like.

Consumer thread.

Is waiting.

So now it will wait.

Okay.

And here in the synchronize, it will put the item and it will notify all the threads which are waiting

on this object.

Right.

So it let me put this like.

Producer thread.

Calling the notify method.

Right.

So it will call the notify method.

So whatever the threads which are waiting on this wait they will get invoked.

So in the main method I can start this producer thread dot start and consumer thread dot start.

Now since they are threads right, they can work parallelly if consumer thread like initiated first.

So what it will do is it is.

False.

Like, uh, if it is a consumer thread invokes first, it's fine, it is false, it becomes true and

it goes inside and wait.

But if producer thread started the first, it goes and it will add it, and consumer thread will got

the item and it will goes out, it will not wait.

So to make sure that consumer goes first let's make producer thread wait for some time.

So producer thread let's keep it thread dot sleep for.

Two seconds, so we have to put trackers.

Exception handling.

Exception handling here.

Okay.

So now in the producer thread it will whenever producer thread will start it will wait for some time.

And this two second will make sure that consumer thread will go first.

So consumer thread when it starts it will try to consume item would not be present.

So it will go and wait.

And after two seconds producer will come and it will add an item and it will invoke it.

So after that, the consumer item will go on.

Right.

So now and you already know the how the monitor lock is working.

Right.

Since they are working both on the same object.

So consumer thread will put a lock first.

Item is not present.

It will goes into wait and when it waits, it will release all the monitor lock here.

And since it release all the monitor lock, when the producer will come, it will, it will able to

get the lock and it will go inside.

And when it call, notify all and it goes out, it will release its lock.

And now it will goes uh again.

Consumer will goes into runnable and it will take the lock again.

So now let's run it.

Consumer thread inside consumer item method.

Consumer thread is waiting.

Producer threat calling the notify method.

So producer threat calling the notify method.

And what it will do is it will goes out of this block.

So let us put that consumer thread, consume the item so that we got to know that it got invoked.

So let's and make it three seconds.

Run.

Consumer thread inside consumer method.

It is waiting.

Producer thread calling the notify method.

Consumer thread.

Consume the item.

So you got it right, how the threads are working and how we have seen the sleep we have seen, uh,

this.

Wait.

Notify.

Right.

So you know that how it can goes into the timed wait.

Expect, uh, time waiting state during sleep and the waiting like wait notify right.

Similarly, whenever DB operation will comes, it will goes automatically into the blocked state.

So and how it goes into the start runnable state.

So it's very easy.

But now there is one assignment for you guys.

You have to implement the producer consumer problem.

It is very important question.

So this is the question.

Two thread, a producer and a consumer share a common fixed size buffer as a queue, so there is a queue.

Both producer is using the same object consumer is consuming from this queue.

The producer job is to generate the data and put into the buffer.

Consumer job is to consume the data from the buffer.

So producer will put some data so it puts some data.

And consumer will consume it.

So it will, uh, free this item, free this, consume it.

Once it is consumed, it will remove from the queue.

Remove from the queue.

The problem is to make sure that the producer won't produce data if the buffer is full.

If the buffer is full, let's say it has producer has produced all, then it should wait, then it should

wait.

It should not put more item.

And the consumer won't consume.

The data buffer is empty if the buffer is empty.

There is no data to consume.

Consumers should wait.

It should not consume it.

So you have to.

It is very similar to what we have done.

But now instead it is they have to work on a queue and they have to do this.

So can you try to implement this?

Producer consumer problem.

Right.

So in the next session.

Right.

So what we will do is I will provide you the solution.

We will discuss the solution.

I will also implement the same.

But I want like first you implement it.

You can share me uh in the comment section your code or you can ping me right.

So let's have the solution.

I will also build my solution and share.

And then also we will see that there is one stop resume.

Suspended method is deprecated in the thread.

We need to understand why and if we don't if this is deprecated how to do that.

Right.

So here in this thread, if you see that when we say that.

This stop method.

This stop method.

This is deprecated.

This is deprecated method.

If this is deprecated method stop then how to stop.

How to terminate the threat.

How to terminate the threat.

We will see that okay.

So yeah, that's all for today.

And please work on this problem before I discuss it.

Because in the next session when I will tell you the solution.

Right.

If you have done it, you will be able to sync up with me better.

Right.

Otherwise you will have lot of doubt.

So please spend some time on building this solution.

Okay, guys.

See you.

Bye.

information alert
Schedule learning time
Learning a little each day adds up. Research shows that students who make learning a habit are more likely to reach their goals. Set time aside to learn and get reminders using your learning scheduler.
Complete Core Java (Collections, Multithreading, Java8 features etc.) in depth with Examples and Code
Rating: 4.6 out of 5
4.6
1,384 ratings
9,774
Students
30 hours
Total
Last updated October 2024
English
English [Auto], Arabic [Auto]
, 
What you'll learn
Fundamentals of JAVA in depth
Multithreading in depth
Collections in depth
JAVA with practical sessions
Description
Fundamentals:

Classes

Object

Constructor etc.

4 pillars

Inheritance

Polymorphism

Abstraction

Encapsulation

Basic Overview of Java:

Procedural vs OOPs

What is Java and what makes it Platform Independent

JDK vs JRE vs JVM

Installation

Setting Class path Environment Variables

Going One Level Deep:

Writing First Java Program

Understanding Classes, different types and Objects

Abstract Classes

Inner Classes etc.

Understanding Variables

Static Variables

Final Variables

Primitive Variables

Object references

Cover Big decimal vs Double

Understanding about String

String Pool

String Immutability

Access Specifiers

Type Casting

Implicit Type Casting

Explicit Type Casting

Understanding Method and Different Types

Cover Return Type

Cover static method

Method parameters

Pass by value vs pass by reference

Overloading etc.

How does Memory Management Happens in Java

Understand about heap and stack memory

Garbage Collector

Understand Constructor

Private Constructor

Default Constructor

Parametrized Constructor

Constructor vs Method

Files and Directories in Java

Read and Write from File using Scanners

Understanding Package and import

Understand POJOs etc.…..

Operators:

Arithmetic Operator

Relational Operator

Short Circuit Operator

Assignment Operator

Logical Operator

Ternary Operator

Bitwise Operator

Enums and its advanced usage

     Control Flow Statements:

If Statement

If Else Statement

If Else Ladder

Switch Statement and when to use

For Loop

While Loop

Do While Loop

Break Statement

Continue Statement

Multithreading and Concurrency:

ThreadPool Executors and Concurrency in Depth

Exception Handling:

Handling of Compile Time and

Handling of Run time errors

Checked and unchecked exception

Generic Programming in Java:

  Understand how to write generic classes and methods in java, and when to use

Java Collections:

List:

Array List

LinkedList

Stack

Queue:

Priority Queue

Dequeue

Set:

HashSet

Tree Set

LinkedHashSet

Map:

Tree Map

HashMap etc.

Java 8 Features:

Functional Interface

Lambda Expression

Stream APIs

Predicates

ForEach method

Default and static method in interface

Who this course is for:
Backend Software engineers
Instructor
Shrayansh Jain
Senior Software Engineer with 9+ Year of Experience
Senior Software Engineer with 9+ Year of Experience and i love sharing knowledge with others too.
I also share my knowledge regarding System Design, Java at Concept and Coding Youtube channel.

I have worked on application which handles 1Billion+ requests per day and also taken care of many projects end to end (from Design to deployment)

Requirements
Eagerness to learn
Get the app
About us
Help and Support
Terms
Privacy policy
Sitemap
Accessibility statement
© 2025 Udemy, Inc.
