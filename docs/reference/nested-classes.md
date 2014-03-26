---
layout: reference
title: "Nested Classes"
category: reference
subcategory: subcategory-2
---

Classes can be nested in other classes

{% highlight kotlin %}
class Outer() {
  private val bar : Int = 1
  class Nested() {
    fun foo() = 2
  }
}

val demo = Outer.Inner().foo() // == 2
{% endhighlight %}

### Inner classes

A class may be marked as *inner* to be able to access members of outer class. Inner classes carry a reference to an object of an outer class:

{% highlight kotlin %}
class Outer() {
  private val bar : Int = 1
  inner class Inner() {
    fun foo() = bar
  }
}

val demo = Outer().Inner().foo() // == 1
{% endhighlight %}

See [Qualified *this*{: .keyword } expressions|({{ site.baseurl }}/docs/reference/language-conventions.html#this-expression) to learn about disambiguation of *this*{: .keyword } in inner classes.
