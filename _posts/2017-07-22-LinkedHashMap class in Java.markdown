---
layout: post
title:  "LinkedHashMap class in Java"
date:   2017-07-22 10:00:00 +0530
tags: [Java, Collections, Java Collections, Java Collections Framework, Map, Hash Table, Linked List, LinkedList, LinkedHashMap, LinkedHashMap class]
comments: true
---

Map is an object that maps keys to values. A map cannot contain duplicate keys.

**LinkedHashMap** class is a hash table and linked list implementation of the **Map** interface. Here, the elements are ordered based on the order they were inserted.

This implementation differs from [HashMap]({{ site.baseurl }}{% post_url 2017-07-21-HashMap class in Java %}){:target="_blank"} in that it maintains a doubly-linked list running through all of its entries. This linked list defines the iteration ordering, which is normally the order in which keys were inserted into the map (insertion order). 

**LinkedHashMap** class permits `null` values and the `null` key.

Java provides the **LinkedHashMap** class as part of the Java Collections Framework. For an overview of the Java Collections Framework, check out my post [Overview of the Java Collections Framework]({{ site.baseurl }}{% post_url 2017-06-19-Overview of the Java Collections Framework %}){:target="_blank"}.

The following example illustrates the **LinkedHashMap** class.

## Example

{% highlight java %}
import java.util.Map;
import java.util.LinkedHashMap;

public class Main {
    public static void main(String[] args) {

        // create a LinkedHashMap
        LinkedHashMap<Integer, String> linkedHashMap = new LinkedHashMap<Integer, String>();

        // add some elements into the LinkedHashMap
        linkedHashMap.put(10, "Red");
        linkedHashMap.put(20, "Blue");
        linkedHashMap.put(50, "Green");
        linkedHashMap.put(60, "Yellow");

        // display the LinkedHashMap
        for(Map.Entry<Integer, String> entry : linkedHashMap.entrySet()) {
            Integer key = entry.getKey();
            String value = entry.getValue();
            System.out.println("Key: " + key + " and " + "Value: " + value);
        }

        // get the value of a specified key
        System.out.println("Value of key 20 is " + linkedHashMap.get(20));

        // check if the LinkedHashMap contains a specified value
        System.out.println("LinkedHashMap contains value \"Green\": " + linkedHashMap.containsValue("Green"));

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
LinkedHashMap contains value "Green": true
{% endhighlight %}

As you can see from the above output, **LinkedHashMap** preserved the insertion order of the elements.

The above program showed the use of some of the common methods of the **LinkedHashMap** class. For a complete list of all the available methods, refer the [official docs].

Now since you know how to use the **LinkedHashMap** class, check out other implementations of the **Map** interface:

* [HashMap class in Java]({{ site.baseurl }}{% post_url 2017-07-21-HashMap class in Java %}){:target="_blank"}
* [TreeMap class in Java]({{ site.baseurl }}{% post_url 2017-07-23-TreeMap class in Java %}){:target="_blank"}

[official docs]: https://docs.oracle.com/javase/9/docs/api/java/util/LinkedHashMap.html
{:target="_blank"}

