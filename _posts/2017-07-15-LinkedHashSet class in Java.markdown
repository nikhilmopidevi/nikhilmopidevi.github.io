---
layout: post
title:  "LinkedHashSet class in Java"
date:   2017-07-15 10:00:00 +0530
tags: [Java, Collections, Java Collections, Java Collections Framework, Set, Hash Table, Linked List, LinkedList, LinkedHashSet, LinkedHashSet class]
comments: true
---

Set is a collection that cannot contain duplicate elements. 

**LinkedHashSet** class is a hash table and linked list implementation of the **Set** interface. That is, it stores its elements in a hash table with a linked list. Here, the insertion order is preserved.

**LinkedHashSet** differs from [HashSet]({{ site.baseurl }}{% post_url 2017-07-14-HashSet class in Java %}) in that it maintains a doubly-linked list running through all of its entries. This linked list defines the iteration ordering, which is the order in which elements were inserted into the set (insertion order).

**LinkedHashSet** class permits the `null` element. It must be noted that a set may contain at most one null element (not more than one because no duplicates are allowed in a set).

Java provides the **LinkedHashSet** class as part of the Java Collections Framework. [Here]({{ site.baseurl }}{% post_url 2017-06-19-Overview of the Java Collections Framework %}) is an overview of the Java Collections Framework.

The following example illustrates the **LinkedHashSet** class.

## Example

{% highlight java %}
import java.util.LinkedHashSet;

public class Main {
    public static void main(String[] args) {

        // create a LinkedHashSet of strings
        HashSet<String> linkedHashSet = new LinkedHashSet<String>();

        // add some elements into the LinkedHashSet
        linkedHashSet.add("red");
        linkedHashSet.add("blue");
        linkedHashSet.add("green");
        linkedHashSet.add("yellow");

        // add null element
        linkedHashSet.add(null);

        // add some duplicate elements
        linkedHashSet.add("blue");
        linkedHashSet.add("green");
        linkedHashSet.add(null);

        // get the number of elements in the LinkedHashSet
        System.out.println("Number of elements in the LinkedHashSet is " + linkedHashSet.size());

        // display the LinkedHashSet
        System.out.println("Current elements in the LinkedHashSet: " + linkedHashSet);

    }
}
{% endhighlight %}

## Output

{% highlight java %}
Number of elements in the LinkedHashSet is 5
Current elements in the LinkedHashSet: [red, blue, green, yellow, null]
{% endhighlight %}

As you can see from the above output, there are no duplicate elements in the **LinkedHashSet**. Also, **LinkedHashSet** preserved the insertion order of the elements.

The above program showed the use of some of the common methods of the **LinkedHashSet** class. For a complete list of all the available methods, refer the [official docs].

Now since you know how to use the **LinkedHashSet** class, check out other implementations of the **Set** interface:

* [HashSet class in Java]({{ site.baseurl }}{% post_url 2017-07-14-HashSet class in Java %})
* [TreeSet class in Java]({{ site.baseurl }}{% post_url 2017-07-16-TreeSet class in Java %})

[official docs]: https://docs.oracle.com/javase/9/docs/api/java/util/LinkedHashSet.html

