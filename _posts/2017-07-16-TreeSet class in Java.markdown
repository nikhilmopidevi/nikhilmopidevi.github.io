---
layout: post
title:  "TreeSet class in Java"
date:   2017-07-16 10:00:00 +0530
tags: [Java, Collections, Java Collections, Java Collections Framework, Set, TreeMap, TreeSet, TreeSet class]
comments: true
---

Set is a collection that cannot contain duplicate elements. 

**TreeSet** class is a **NavigableSet** implementation based on a **TreeMap**. It stores its elements in a red-black tree, which is a self-balancing binary search tree. 

**TreeSet** is substantially slower than [HashSet]({{ site.baseurl }}{% post_url 2017-07-14-HashSet class in Java %}){:target="_blank"}, but the elements are ordered based on their value.

**TreeSet** differs from [HashSet]({{ site.baseurl }}{% post_url 2017-07-14-HashSet class in Java %}){:target="_blank"} in that it orders its elements in ascending order. That is, regardless of the insertion order of the elements, all elements are ordered in ascending order (their natural ordering to be precise).

**TreeSet** class doesn't allow the `null` element.

Java provides the **TreeSet** class as part of the Java Collections Framework. For an overview of the Java Collections Framework, check out my post [Overview of the Java Collections Framework]({{ site.baseurl }}{% post_url 2017-06-19-Overview of the Java Collections Framework %}){:target="_blank"}.

The following example illustrates the **TreeSet** class.

## Example

{% highlight java %}
import java.util.TreeSet;

public class Main {
    public static void main(String[] args) {

        // create a TreeSet of strings
        TreeSet<String> treeSet = new TreeSet<String>();

        // add some elements into the TreeSet
        treeSet.add("red");
        treeSet.add("blue");
        treeSet.add("green");
        treeSet.add("yellow");

        // add some duplicate elements
        treeSet.add("blue");
        treeSet.add("green");

        // get the number of elements in the TreeSet
        System.out.println("Number of elements in the TreeSet is " + treeSet.size());

        // display the TreeSet
        System.out.println("Current elements in the TreeSet: " + treeSet);
    }
}
{% endhighlight %}

## Output

{% highlight java %}
Number of elements in the TreeSet is 4
Current elements in the TreeSet: [blue, green, red, yellow]
{% endhighlight %}

As you can see from the above output, there are no duplicate elements in the **TreeSet**. Also, **TreeSet** ordered the elements in their ascending order.

The above program showed the use of some of the common methods of the **TreeSet** class. For a complete list of all the available methods, refer the [official docs].

Now since you know how to use the **TreeSet** class, check out other implementations of the **Set** interface:

* [HashSet class in Java]({{ site.baseurl }}{% post_url 2017-07-14-HashSet class in Java %}){:target="_blank"}
* [LinkedHashSet class in Java]({{ site.baseurl }}{% post_url 2017-07-15-LinkedHashSet class in Java %}){:target="_blank"}

[official docs]: https://docs.oracle.com/javase/9/docs/api/java/util/TreeSet.html
{:target="_blank"}

