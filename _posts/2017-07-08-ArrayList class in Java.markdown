---
layout: post
title:  "ArrayList class in Java"
date:   2017-07-08 10:00:00 +0530
tags: [Java, Collections, Java Collections, Java Collections Framework, Array List, ArrayList, ArrayList class]
comments: true
---

**ArrayList** is a resizable-array implementation of the **List** interface. ArrayList offers an alternative to traditional arrays which are fixed in size and cannot grow beyond the capacity specified during initialization.

The **ArrayList** class also offers a lot of useful methods which we can use in our programs. It implements all optional list operations, and permits all elements, including `null`.

Java provides the **ArrayList** class as part of the Java Collections Framework. [Here]({{ site.baseurl }}{% post_url 2017-06-19-Overview of the Java Collections Framework %}) is an overview of the Java Collections Framework.

The following example illustrates the **ArrayList** class.

## Example

{% highlight java %}
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {

        // create an array list of strings
        ArrayList<String> arrayList = new ArrayList<String>();

        // add some strings into the array list
        arrayList.add("red");
        arrayList.add("blue");
        arrayList.add("green");
        arrayList.add("yellow");

        // display the array list
        System.out.println("Current elements in the array list: " + arrayList);

        // add strings at the specified index
        arrayList.add(0, "black");
        arrayList.add(2, "white");

        // display the array list
        System.out.println("Current elements in the array list: " + arrayList);

        // display the string at a specified index
        System.out.println("Element at index " + 3 + " is " + arrayList.get(3));

        // replace the string at a specified index
        arrayList.set(3, "orange");

        // remove the string at a specified index
        arrayList.remove(1);

        // check if the array list contains a specified string
        System.out.println("Array list contains green: " + arrayList.contains("green"));

        // get the size of the array list
        System.out.println("Number of elements in the array list is " + arrayList.size());
        
    }
}
{% endhighlight %}

## Output

{% highlight java %}
Current elements in the array list: [red, blue, green, yellow]
Current elements in the array list: [black, red, white, blue, green, yellow]
Element at index 3 is blue
Array list contains green: true
Number of elements in the array list is 5
{% endhighlight %}

The above program showed the use of some of the common methods of the **ArrayList** class. For a complete list of all the available methods, refer the [official docs].

Now since you know how to use the **ArrayList** class, check out another implementation of the **List** interface, the [LinkedList class in Java]({{ site.baseurl }}{% post_url 2017-07-09-LinkedList class in Java %}).

[official docs]: https://docs.oracle.com/javase/9/docs/api/java/util/ArrayList.html

