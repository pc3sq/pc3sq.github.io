---
layout: post
title:  "Blocks vs. Procs vs. Lambdas"
date:   2014-07-11
categories: technical blog
tags: week6
---

<section>
	<h2>Blocks vs. Procs vs. Lambdas</h2>
	<article>
		<h3>Blocks, Procs, and Lambdas Are Closures</h3>
		<p>In programming, a closure is a scope created by calling some outer function that remains available to any function created within that scope even after the call to the function has returned. Basically, closures are one way to make a local variable available to a higher level scope. </p>
		<p>Blocks, Procs, and Lambdas are all closures, but what what are their differences?</p>
	</article>
	<article>
		<h3>Blocks</h3>
		<p> Blocks are considered a one time use block of code, nothing more than just syntax. The block in the following code is "element * 2":</p>
		<pre> 
array.each do | element |
element * 2
end
		</pre>
	</article>
	<article>
		<h3>Procs, Short for Procedures</h3>
		<p> Procs are blocks BUT, they are blocks created using the Proc class. In other words, Procs are objects of the Proc class and inherit the Proc class methods when they are created. Blocks, being simply syntax and not objects of anything, don't have methods we can call on them. Furthermore, using Procs means we don't have to repeat blocks throughout our code. When we want to use a Proc, we simply refer to it by name. Here's an example of what procs can do:
		</p>
		<pre>
a_proc = Proc.new { puts "Hi, I'm a proc." }

a_proc.call  # prints 'Hi, I'm a proc.'
a_proc.class # returns 'Proc'
da_proc = a_proc   # da_proc is now assigned to a_proc, a Proc instance
da_proc   # returns a proc object '&lt;Proc:0x000001018594e8@(irb#1):30&gt;'
		</pre>
		<p> Another to thing to keep in mind is that Procs are drop-in code snippets. This becomes important when distinguishing it from Lambdas. More on this in the Lambda section below.
		</p>
	</article>
	<article>
		<h3>Lambdas</h3>
		<h5>Lambas, Another Name For Anonymous Functions</h5>
		<p> Remember anonymous functions in Javascript? It's ok if you don't. Anonymous functions, in Javascript and other languages like Ruby, are simply functions that have no identifiers variable names. Thus, anonymous functions are also not saved for multiuse. This makes them different from Procs but this doesn't make Lambdas exactly like simple code blocks either.
		</p>
		<h5>Lambas Are Like Methods; They Check For # of Arguments</h5>
		<p>One difference between Procs and Lambdas is that Lambdas, in Ruby, check for the number of arguments; Procs don't.
		</p>
		<h5>Lambdas Are Like Methods; They Don't Override The Calling Method's Returns</h5>
		<p> Remember Procs are just drop-in code snippets. In this sense, Procs are like part of the calling method. So once the Proc returns someting, it is as if the calling method itself returns something, thus exiting the calling method entirely. For example:</p>
		<pre>
def when_to_exit
Proc.new { return "we just returned from the block" }.call
return "we just returned from the calling method"
end

puts when_to_exit #=> "we just returned from the block"
		</pre>
		Conversely, ambdas act more like methods because they do not override the calling methods returns. lamdas will let the calling method run its course even after the lambda has returned something. Lamdbas are therefore useful as callback functions.</p>
		<pre>
def when_to_exit
Proc.new { return "we just returned from the block" }.call
return "we just returned from the calling method"
end

puts when_to_exit #=> "we just returned from the calling method"
		</pre>
	</article>
	<article>
		<h5>Practical Summary</h5>
		<p>Use blocks when you don't need to use the blocks elsewhere in your code.</p>
		<p>Use Procs only if you want a resuable block that acts like it's part of the calling method and therefore exits the calling method.</p>
		<p>But in most cases, you want your reusable block to act more like a method and return something the calling method can use (i.e. a callback). For these more general purpose cases, use lambda.
		</p>
	</article>
</section>

<section>
	<h2>References</h2>
	<a href="http://rubymonk.com/learning/books/4-ruby-primer-ascent/chapters/18-blocks/lessons/64-blocks-procs-lambdas">Ruby Monk: Block, Procs, & Lambdas</a>
	<br>
	<br>
	<a href="http://awaxman11.github.io/blog/2013/08/05/what-is-the-difference-between-a-block/">Adam Waxman: What Is the Difference Between a Block, a Proc, and a Lambda in Ruby?</a>
</section>