---
layout: post
title:  "LinkedList class in Java"
date:   2017-07-09 10:00:00 +0530
tags: [Java, Collections, Java Collections, Java Collections Framework, List, Linked List, LinkedList, LinkedList class]
comments: true
---

**LinkedList** is a doubly-linked list implementation of the **List** and **Deque** interfaces.

The **LinkedList** class also offers a lot of useful methods which we can use in our programs. It implements all optional list operations, and permits all elements, including `null`.

Java provides the **LinkedList** class as part of the Java Collections Framework. For an overview of the Java Collections Framework, check out my post [Overview of the Java Collections Framework]({{ site.baseurl }}{% post_url 2017-06-19-Overview of the Java Collections Framework %}){:target="_blank"}.

The following example illustrates the **LinkedList** class.

## Example

{% highlight java %}
import java.util.LinkedList;

public class Main {
    public static void main(String[] args) {

        // create a linked list of strings
        LinkedList<String> linkedList = new LinkedList<String>();

        // add some strings into the linked list
        linkedList.add("red");
        linkedList.add("blue");
        linkedList.add("green");
        linkedList.add("yellow");

        // display the linked list
        System.out.println("Current elements in the linked list: " + linkedList);

        // add strings at the specified index
        linkedList.add(2, "white");
        linkedList.add(4, "black");

        // add string at the beginning of the linked list
        linkedList.addFirst("violet");

        // add string at the end of the linked list
        linkedList.addLast("pink");

        // display the linked list
        System.out.println("Current elements in the linked list: " + linkedList);

        // display the string at a specified index
        System.out.println("Element at index " + 3 + " is " + linkedList.get(3));

        // replace the string at a specified index
        linkedList.set(3, "orange");

        // remove the string at a specified index
        linkedList.remove(1);

        // remove the string at the beginning of the linked list
        linkedList.removeFirst();

        // remove the string at the end of the linked list
        linkedList.removeLast();

        // check if the linked list contains a specified string
        System.out.println("Linked list contains green: " + linkedList.contains("green"));

        // get the size of the linked list
        System.out.println("Number of elements in the linked list is " + linkedList.size());

    }
}
{% endhighlight %}

## Output

{% highlight java %}
Current elements in the linked list: [red, blue, green, yellow]
Current elements in the linked list: [violet, red, blue, white, green, black, yellow, pink]
Element at index 3 is white
Linked list contains green: true
Number of elements in the linked list is 5
{% endhighlight %}

The above program showed the use of some of the common methods of the **LinkedList** class. For a complete list of all the available methods, refer the [official docs].

Now since you know how to use the **LinkedList** class, check out another implementation of the **List** interface, the [ArrayList class in Java]({{ site.baseurl }}{% post_url 2017-07-08-ArrayList class in Java %}){:target="_blank"}.

[official docs]: https://docs.oracle.com/javase/9/docs/api/java/util/LinkedList.html
{:target="_blank"}

