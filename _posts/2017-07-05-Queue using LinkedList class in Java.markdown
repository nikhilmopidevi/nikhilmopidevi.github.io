---
layout: post
title:  "Queue using LinkedList class in Java"
date:   2017-07-05 10:00:00 +0530
tags: [Java, Collections, Java Collections, Java Collections Framework, Queue, Linked List, LinkedList, LinkedList class, Deque]
comments: true
---

Queue is a linear data structure which orders elements in a First-In-First-Out (FIFO) manner, where the first element inserted is the first one to be removed.

In this post, we'll see how to implement a queue using the **LinkedList** class. Java provides the **LinkedList** class as part of the Java Collections Framework. [Here]({{ site.baseurl }}{% post_url 2017-06-19-Overview of the Java Collections Framework %}) is an overview of the Java Collections Framework.

Some important methods provided by the **LinkedList** class for implementing a queue are:
1. add(E element)
2. peek()
3. poll()
4. offer(E element)
5. element()
6. remove()
7. isEmpty()

**LinkedList** class permits all elements, including `null`. But it is not recommended to insert nulls because `null` is used as a special return value by various methods to indicate that the deque is empty.

The following example demonstrates how to implement a queue using the **LinkedList** class.

## Example

{% highlight java %}
import java.util.LinkedList;

public class Main {
    public static void main(String[] args) {

        //Creates a queue of integers
        LinkedList<Integer> queue = new LinkedList<Integer>();

        //Pushes some integers into the queue
        queue.add(2);
        queue.add(5);
        queue.add(6);

        //Peeks into the queue
        System.out.println("Current element at the top of the queue: " + queue.peek());

        //Removes one integer from the queue
        System.out.println("Element removed from the queue: " + queue.poll());

        //Iterates through the queue
        System.out.print("Current elements in the queue: ");
        while(!queue.isEmpty()) {
            System.out.print(queue.poll() + " ");
        }

    }
}
{% endhighlight %}

## Output

{% highlight java %}
Current element at the top of the queue: 2
Element removed from the queue: 2
Current elements in the queue: 5 6 
{% endhighlight %}

Let us look at the methods available to us.

## Methods 

#### **1) add(E element)**
This method inserts an element at the end of the queue represented by this list. It returns **true** if the insertion is successful, or **false** if it is not. 

If no space is currently available, this method throws an `'IllegalStateException'`.

#### **2) peek()**
It retrieves, but does not remove, the head of this queue (first element of this list). It returns `null` if the queue is empty.

#### **3) poll()**
It retrieves and removes the head of this queue. In other words, it removes and returns the first element of this list. 

If the queue is empty, it returns `null`.
 
#### **4) isEmpty()**
This method tests if the queue is empty. It returns **true** if the queue is empty or **false** otherwise.

The methods **offer(E element)**, **element()**, and **remove()** function similar to the methods **add(E element)**, **peek()**, and **poll()** respectively but they don't throw any exception if insertion is not possible, or return `null` if the queue is empty.

Now since you know how to implement a queue using the **LinkedList** class, check out how to create a [Queue using ArrayDeque]({{ site.baseurl }}{% post_url 2017-07-06-Queue using ArrayDeque class in Java %}).


