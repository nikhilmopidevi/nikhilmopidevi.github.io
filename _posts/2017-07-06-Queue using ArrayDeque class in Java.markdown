---
layout: post
title:  "Queue using ArrayDeque class in Java"
date:   2017-07-06 10:00:00 +0530
tags: [Java, Collections, Java Collections, Java Collections Framework, Queue, ArrayDeque, ArrayDeque class, Deque]
comments: true
---

Queue is a linear data structure which orders elements in a First-In-First-Out (FIFO) manner, where the first element inserted is the first one to be removed.

In this post, we'll see how to implement a queue using **ArrayDeque** — a resizable array implementation of the **Deque** interface. Java provides the **ArrayDeque** class as part of the Java Collections Framework. [Here]({{ site.baseurl }}{% post_url 2017-06-19-Overview of the Java Collections Framework %}) is an overview of the Java Collections Framework.

Some important methods provided by the **ArrayDeque** class for implementing a queue are:
1. add(E element)
2. peek()
3. poll()
4. offer(E element)
5. element()
6. remove()
7. isEmpty()

Array deques have no capacity restrictions, which means they grow as necessary to support usage.

**ArrayDeque** class prohibits `null` elements. Even if it had allowed, it is not recommended to insert nulls because `null` is used as a special return value by various methods to indicate that the deque is empty.

According to Java Docs, **ArrayDeque** class is likely to be faster than [Stack]({{ site.baseurl }}{% post_url 2017-06-25-Stack class in Java %}) when used as a stack, and faster than [LinkedList](({{ site.baseurl }}{% post_url 2017-07-05-Queue using LinkedList class in Java %})) when used as a queue.

The following example demonstrates how to implement a queue using the **ArrayDeque** class.

## Example

{% highlight java %}
import java.util.ArrayDeque;

public class Main {
    public static void main(String[] args) {

        //Creates a queue of integers
        ArrayDeque<Integer> queue = new ArrayDeque<Integer>();

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
This method inserts an element at the end of the deque.

#### **2) peek()**
It retrieves, but does not remove, the head of the queue represented by this deque. It returns `null` if the deque is empty.

#### **3) poll()**
It retrieves and removes the head of the queue represented by this deque. If the deque is empty, it returns `null`.
 
#### **4) isEmpty()**
This method returns **true** if the deque contains no elements, or **false** otherwise.

The **offer(E element)** method is exactly similar to the **add(E element)** method. **element()** and **remove()** methods also function similar to the methods **peek()** and **poll()** respectively but don't return `null` if the queue is empty.

Now since you know how to implement a queue using the **ArrayDeque** class, check out how to create a [Queue using LinkedList]({{ site.baseurl }}{% post_url 2017-07-05-Queue using LinkedList class in Java %}).

