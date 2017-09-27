---
layout: post
title:  "HashMap class in Java"
date:   2017-07-21 10:00:00 +0530
tags: [Java, Collections, Java Collections, Java Collections Framework, Map, Hash Table, HashMap, HashMap class]
comments: true
---

Map is an object that maps keys to values. A map cannot contain duplicate keys.

**HashMap** class is a hash table based implementation of the **Map** interface. It makes no guarantees concerning the order of iteration; in particular, it does not guarantee that the order will remain constant over time.

**HashMap** class permits `null` values and the `null` key.

Java provides the **HashMap** class as part of the Java Collections Framework. [Here]({{ site.baseurl }}{% post_url 2017-06-19-Overview of the Java Collections Framework %}) is an overview of the Java Collections Framework.

The following example illustrates the **HashMap** class.

## Example

{% highlight java %}
import java.util.Map;
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {

        // create a HashMap
        HashMap<Integer, String> hashMap = new HashMap<Integer, String>();

        // add some elements into the HashMap
        hashMap.put(10, "Red");
        hashMap.put(20, "Blue");
        hashMap.put(50, "Green");
        hashMap.put(60, "Yellow");

        // display the HashMap
        for(Map.Entry<Integer, String> entry : hashMap.entrySet()) {
            Integer key = entry.getKey();
            String value = entry.getValue();
            System.out.println("Key: " + key + " and " + "Value: " + value);
        }

        // get the value of a specified key
        System.out.println("Value of key 20 is " + hashMap.get(20));

        // check if the HashMap contains a specified key
        System.out.println("HashMap contains key 100: " + hashMap.containsKey(100));

        // check if the HashMap contains a specified value
        System.out.println("HashMap contains value \"Green\": " + hashMap.containsValue("Green"));

    }
}
{% endhighlight %}

## Output

{% highlight java %}
Key: 50 and Value: Green
Key: 20 and Value: Blue
Key: 10 and Value: Red
Key: 60 and Value: Yellow
Value of key 20 is Blue
HashMap contains key 100: false
HashMap contains value "Green": true
{% endhighlight %}

As you can see from the above output, **HashMap** didn't preserve the insertion order of the elements.

The above program showed the use of some of the common methods of the **HashMap** class. For a complete list of all the available methods, refer the [official docs].

Now since you know how to use the **HashMap** class, check out other implementations of the **Map** interface:

* [LinkedHashMap class in Java]({{ site.baseurl }}{% post_url 2017-07-22-LinkedHashMap class in Java %})
* [TreeMap class in Java]({{ site.baseurl }}{% post_url 2017-07-23-TreeMap class in Java %})

[official docs]: https://docs.oracle.com/javase/9/docs/api/java/util/HashMap.html

