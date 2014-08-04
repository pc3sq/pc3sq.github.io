---
layout: post
title:  "Structuring Real World Objects w/ Classes & Data Structures"
date:   2014-07-04
categories: technical blog
tags: week5
---

<section>
	<h2>Structuring Real World Objects w/ Classes &amp; Data Structures</h2>
	<article>
		<h3>Classes Are Templates For Objects</h3>
		<p>
			Classes allow us to describe a template for objects in terms of what they are (aka characteristics) and what they can do (aka methods).
		</p>
	</article>
	<article>
		<h3>Objects Are Instances of Classes</h3>
		<p>
			As templates, classes aren't unfinished products. A class is an outline that needs to be filled out, like a <a href="http://www.elibs.com/">MadLibs</a>. When you decide to create an filled out class, you are actually instantiating, or create an instance of, the class. This instance of a class is known as an "object" of that class.
		</p>
	</article>
	<article>
		<h3>Instance variables and methods</h3>
		<p>
			When you instantiate an object, it comes packaged with its own instance variables and methods. These instance variables and methods come into existence when the object is created. The scope of these instance variables and methods are limited to the particular object as well. One object cannot access the instance variables and methods of any other object even if they are created from the same class.
		</p>
		<p>
			Instance variables are important for passing around data between your instance methods. Instance variables are preceded by an '@' sign like '@color'.
		</p>
	</article>
	<article>
		<h3>A T-Shirt Example</h3>
		<p>
			You want to make t-shirts and you think have a form for these t-shirts would help keep you organized. What can the t-shirts be? What can happen to the t-shirts? These are the considerations when creating your Tshirt (classes are capitalized by Ruby convention) class.
		</p>
		<p>
			You decided that your Tshirt class should have a particular size and color, similar to what you would have on your form. Size and color are characteristics your t-shirts can have. You also want to mark off if your t-shirts have been worn. Being worn is something that can happen to your t-shirts so you can describe this action as a method in your Tshirt class.</p>
		<p> And here is the Tshirt class.</p>
		<pre>
class Tshirt 
def initialize (size, color)
@size = size 	# assigns size to the @size instance variable
@color = color	 # assigns color to the @color instance variable
@clean = true	#@clean is an instance variable assigned true
end

def worn
@clean = false
end
end
		</pre>
		<p>
			Notice the three instance variables: @size, @color, @clean. Your @size, @color, and  @clean are variables that contain data that can now be passed around to different instance methods when you create a new object of your Tshirt. You can create a new object by using Ruby's 'new' constructor method like this:
		</p>
		<pre>
wacky_t = Tshirt.new("small", "red")
		</pre>
		<p>
			Notice the two instance methods: Tshirt#initialize and Tshirt#worn. Tshirt#initialize organizes your characteristics and determines whether your characteristics have default values - like @clean = true in our example - or you can pass in arguments to designate your characteristics like your size or color.
		</p>
		<p>
			Tshirt#worn sets the instance variable @clean to false to indicate the Tshirt is dirty after it is worn.
		</p>
	</article>
	<article>
		<h3>Want to Explore Further?</h3>
		<p>
			Try the more complete Tshirt class below with some driver code to show you want can be done. Take notice of the attribute accessor method 'attr_accessor' which allows you to read and write over the instance variables.
		</p>
		<pre>
class Tshirt
attr_accessor :size, :color, :clean 
def initialize (size, color)
@size = size 	# assigns size to the @size instance variable
@color = color	 # assigns color to the @color instance variable
@clean = true	#@clean is an instance variable assigned true
end

def wash
@clean = true
end

def worn
@clean = false
end
end

#Driver code

ruby = Tshirt.new("small", "red")

puts ruby.size
puts ruby.color

puts "This t-shirt is clean. Is it clean? #{ruby.clean.to_s.capitalize}"

ruby.worn
puts "This t-shirt was worn. Is it clean? #{ruby.clean.to_s.capitalize}"

ruby.wash
puts "This t-shirt is clean. Is it clean? #{ruby.clean.to_s.capitalize}"
	</pre>
	</article>
</section>