---
layout: post
title:  "HashSet class in Java"
date:   2017-07-14 10:00:00 +0530
tags: [Java, Collections, Java Collections, Java Collections Framework, Set, Hash Table, HashSet, HashSet class]
comments: true
---

Set is a collection that cannot contain duplicate elements. 

**HashSet** class implements the **Set** interface, backed by a hash table (actually a **HashMap** instance). That is, it stores its elements in a hash table.

**HashSet** has best performance among all the implementations. But it makes no guarantees concerning the order of iteration; in particular, it does not guarantee that the order will remain constant over time. 

**HashSet** class permits the `null` element. It must be noted that a set may contain at most one null element (not more than one because no duplicates are allowed in a set).

Java provides the **HashSet** class as part of the Java Collections Framework. [Here]({{ site.baseurl }}{% post_url 2017-06-19-Overview of the Java Collections Framework %}) is an overview of the Java Collections Framework.

The following example illustrates the **HashSet** class.

## Example

{% highlight java %}
import java.util.HashSet;

public class Main {
    public static void main(String[] args) {

        // create a HashSet of strings
        HashSet<String> hashSet = new HashSet<String>();

        // add some elements into the HashSet
        hashSet.add("red");
        hashSet.add("blue");
        hashSet.add("green");
        hashSet.add("yellow");

        // add null element
        hashSet.add(null);

        // add some duplicate elements
        hashSet.add("blue");
        hashSet.add("green");
        hashSet.add(null);

        // get the number of elements in the HashSet
        System.out.println("Number of elements in the HashSet is " + hashSet.size());

        // display the HashSet
        System.out.println("Current elements in the HashSet: " + hashSet);

    }
}
{% endhighlight %}

## Output

{% highlight java %}
Number of elements in the HashSet is 5
Current elements in the HashSet: [red, null, green, blue, yellow]
{% endhighlight %}

As you can see from the above output, there are no duplicate elements in the **HashSet**. Also, **HashSet** didn't preserve the insertion order of the elements.

The above program showed the use of some of the common methods of the **HashSet** class. For a complete list of all the available methods, refer the [official docs].

Now since you know how to use the **HashSet** class, check out other implementations of the **Set** interface:

* [LinkedHashSet class in Java]({{ site.baseurl }}{% post_url 2017-07-15-LinkedHashSet class in Java %})
* [TreeSet class in Java]({{ site.baseurl }}{% post_url 2017-07-16-TreeSet class in Java %})

[official docs]: https://docs.oracle.com/javase/9/docs/api/java/util/HashSet.html

