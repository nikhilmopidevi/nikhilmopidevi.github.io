---
layout: post
title:  "TreeMap class in Java"
date:   2017-07-23 10:00:00 +0530
tags: [Java, Collections, Java Collections, Java Collections Framework, Map, TreeMap, TreeMap class]
comments: true
---

Map is an object that maps keys to values. A map cannot contain duplicate keys.

**TreeMap** class is a red-black tree based **NavigableMap** implementation. It stores its elements in a red-black tree, which is a self-balancing binary search tree.

**TreeMap** is substantially slower than [HashMap]({{ site.baseurl }}{% post_url 2017-07-21-HashMap class in Java %}){:target="_blank"}, but the elements are ordered based on their value.

**TreeMap** differs from [HashMap]({{ site.baseurl }}{% post_url 2017-07-21-HashMap class in Java %}){:target="_blank"} in that it orders its elements in ascending order of their keys. That is, regardless of the insertion order of the elements, all elements are ordered in ascending order of their keys (their natural ordering to be precise).

**TreeMap** class permits `null` values but not the `null` key.

Java provides the **TreeMap** class as part of the Java Collections Framework. For an overview of the Java Collections Framework, check out my post [Overview of the Java Collections Framework]({{ site.baseurl }}{% post_url 2017-06-19-Overview of the Java Collections Framework %}){:target="_blank"}.

The following example illustrates the **TreeMap** class.

## Example

{% highlight java %}
import java.util.Map;
import java.util.TreeMap;

public class Main {
    public static void main(String[] args) {

        // create a TreeMap
        TreeMap<Integer, String> treeMap = new TreeMap<Integer, String>();

        // add some elements into the TreeMap
        treeMap.put(50, "Green");
        treeMap.put(20, "Blue");
        treeMap.put(60, "Yellow");
        treeMap.put(10, "Red");

        // display the TreeMap
        for(Map.Entry<Integer, String> entry : treeMap.entrySet()) {
            Integer key = entry.getKey();
            String value = entry.getValue();
            System.out.println("Key: " + key + " and " + "Value: " + value);
        }

        // get the value of a specified key
        System.out.println("Value of key 20 is " + treeMap.get(20));

        // check if the TreeMap contains a specified key
        System.out.println("TreeMap contains key 100: " + treeMap.containsKey(100));

        // check if the TreeMap contains a specified value
        System.out.println("TreeMap contains value \"Green\": " + treeMap.containsValue("Green"));

    }
}
{% endhighlight %}

## Output

{% highlight java %}
Key: 10 and Value: Red
Key: 20 and Value: Blue
Key: 50 and Value: Green
Key: 60 and Value: Yellow
Value of key 20 is Blue
TreeMap contains key 100: false
TreeMap contains value "Green": true
{% endhighlight %}

As you can see from the above output, **TreeMap** ordered the elements in ascending order of their keys.

The above program showed the use of some of the common methods of the **TreeMap** class. For a complete list of all the available methods, refer the [official docs].

Now since you know how to use the **TreeMap** class, check out other implementations of the **Map** interface:

* [HashMap class in Java]({{ site.baseurl }}{% post_url 2017-07-21-HashMap class in Java %}){:target="_blank"}
* [LinkedHashMap class in Java]({{ site.baseurl }}{% post_url 2017-07-22-LinkedHashMap class in Java %}){:target="_blank"}

[official docs]: https://docs.oracle.com/javase/9/docs/api/java/util/TreeMap.html
{:target="_blank"}

