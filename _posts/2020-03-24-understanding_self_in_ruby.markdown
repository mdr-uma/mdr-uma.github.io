---
layout: post
title:      "Understanding `self` in Ruby"
date:       2020-03-24 19:29:34 +0000
permalink:  understanding_self_in_ruby
---



**What is self?**
You may have heard people say that everything in Ruby is an object. If that's true it means that every piece of code you write "belongs" to some object.

self is a special variable that points to the object that "owns" the currently executing code. Ruby uses self everwhere:

For instance variables: @myvar
For method and constant lookup
When defining methods, classes and modules.
In theory, self is pretty obvious. But in practice, it's easy for tricky situations to pop up. 

**Examples of self**
*Inside of an instance method*
In the code below, reflect is an instance method. It belongs to the object we created via Ghost.new. So self points to that object.

class Ghost
  def reflect
    self
  end
end

g = Ghost.new
g.reflect == g # => true
Inside of a class method
For this example, reflect is a class method of Ghost. With class methods, the class itself "owns" the method. self points to the class.

class Ghost
  def self.reflect
    self
  end
end

Ghost.reflect == Ghost # => true
It works the same with "class" methods inside of modules. For example:

module Ghost
  def self.reflect
    self
  end
end 
Ghost.reflect == Ghost # => true
Remember, classes and modules are treated as objects in Ruby. So this behavior isn't that different from the instance method behavior we saw in the first example.

*Inside of a class or module definition*
One feature of Ruby that makes it such a good fit for frameworks like Rails is that you can execute arbitrary code inside class and module definitions. When you put code inside of a class/module definition, it runs just like any other Ruby code. The only real difference is the value of self.

As you can see below, self points to the class or module that's in the process of being defined.

class Ghost
  self == Ghost # => true
end 

module Mummy
  self == Mummy # => true
end 

