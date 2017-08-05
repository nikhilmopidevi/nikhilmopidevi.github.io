---
layout: post
title:  "Stack class in Java"
date:   2017-06-25 10:00:00 +0530
tags: [Java, Collections, Java Collections, Java Collections Framework, Stack, Stack class]
comments: true
---

Stack is a linear data structure which follows the Last-In-First-Out (LIFO) approach, where the last element inserted is the first one to be removed.

In this post, we'll see how to use the **Stack** class in Java to create a stack. Java provides the **Stack** class as part of the Java Collections Framework. [Here]({{ site.baseurl }}{% post_url 2017-06-19-Overview of the Java Collections Framework %}) is an overview of the Java Collections Framework.

The following example illustrates how to use the **Stack** class in Java.

## Example

{% highlight java %}
import java.util.Stack;

public class Main {
    public static void main(String[] args) {

        //Creates a stack of integers
        Stack<Integer> stack = new Stack<Integer>();

        //Pushes some integers into the stack
        stack.push(2);
        stack.push(5);
        stack.push(6);

        //Peeks into the stack
        System.out.println("Current element at the top of the stack: " + stack.peek());

        //Pops one integer from the stack
        System.out.println("Element popped from the stack: " + stack.pop());

        //Iterates through the stack
        System.out.print("Current elements in the stack: ");
        while(!stack.empty()) {
            System.out.print(stack.pop() + " ");
        }
    }
}
{% endhighlight %}

## Output

{% highlight java %}
Current element at the top of the stack: 6
Element popped from the stack: 6
Current elements in the stack: 5 2 
{% endhighlight %}

Now, let's look at the methods provided by the **Stack** class.

## Methods 

#### **1) push(E element)**
This method pushes an element onto the top of the stack.

Consider a stack with the following elements from top: **"Banana"** **"Apple"** 
{% highlight java %}
stack.push("Orange");
{% endhighlight %}

This method pushes the string **"Orange"** to the top of the stack. Now, the elements in the stack are: **"Orange"** **"Banana"** **"Apple"**

#### **2) pop()**
This method removes and returns the element at the top of the stack. If the stack is empty, an `‘EmptyStackException’` exception is thrown.
{% highlight java %}
String fruit = stack.pop(); //stores the returned string in the variable 'fruit'
{% endhighlight %}

This method removes and returns the string **"Orange"** which is at the top of the stack.

#### **3) peek()**
It returns the element at the top of the stack, but doesn't remove it. As the name indicates, it is similar to peeking at the top of the stack.

{% highlight java %}
String fruit = stack.peek(); //stores the returned string in the variable 'fruit'
{% endhighlight %}

This call to the method returns the string **"Banana"** which is at the top of the stack, but doesn't remove it from the stack.

#### **4) empty()**
This method tests if the stack is empty. It returns **true** if the stack is empty or **false** otherwise.

{% highlight java %}
boolean result = stack.empty(); //stores the returned value in the variable 'result'
{% endhighlight %}

Current elements in the stack: **"Banana"** **"Apple"**

In this case, the call to the method returns **false**, because the stack is not empty.

#### **5) search(E element)**
This method searches the stack for the given element. If the element is found, it returns the position of the element from the top of the stack, otherwise it returns **-1**.

{% highlight java %}
int position = stack.search("Apple"); //stores the returned value in the variable 'position'
{% endhighlight %}

This call to the method returns the value **2**, because the string **"Apple"** is at second position from the top of the stack.

Usually, a stack doesn't allow searching through its elements without popping them out. But this method allows that, and exposes all the elements of the stack. For this reason and others, **Stack** class isn't preferred. Instead, an implementation of the Deque interface such as ArrayDeque or LinkedList are typically used.

Now since you know how to use the **Stack** class in Java, check out other ways to create a stack:

* [Stack using ArrayDeque]()
* [Stack using LinkedList]()

