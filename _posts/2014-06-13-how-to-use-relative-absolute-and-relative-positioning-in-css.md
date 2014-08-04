---
layout: post
title:  "How to Use Relative, Absolute, & Relative Positioning in CSS"
date:   2014-06-13
categories: technical blog
tags: week2
---

<section>
	<h2>How to Use Relative, Absolute, &amp; Relative Positioning in CSS</h2>
	<article>
		<h3>Static Positioning, Where It Would Normally Be</h3>
		<p>When thinking about positioning, start by thinking how a document would present it's information by default. In the western world, we would think that text, for example, starts at the top left. So, let's start with a simple black canvas with the label "black canvass" and see what that looks like:</p>
		<div class="example"> <p>black canvass</p></div>
		<p>Here, the label, "black canvass", starts at the upper left corner because this is the default positioning known as static. Static positioning simply means the label will position itself where it naturally would in a document. Since this is the default, there is no need to declare it explicitly unless you are overriding some other styling elsewhere in your css. Here is an example of the latter case:</p>
		<p class="code"> p { position: static; } </p>
	</article>

	<article>
		<h3>Relative Positioning, Relative To Where It Would Normally Be</h3>
		<p>One way to move the label is to offset it relative from where the label would naturally occur. For example, let's say I want to move it out of the black canvass towards the upper left corner.</p>
		<br>
		<br>
		<div class="example"> <p class="relative">black canvass</p></div>
		<p>The label has moved out of the box because I move it 30px up and 50px to the left by using the following css:</p>
		<p class="code"> div { <br>
		&nbsp;&nbsp;&nbsp;&nbsp;position: relative;<br>
		&nbsp;&nbsp;&nbsp;&nbsp;bottom: 30px;<br>
		&nbsp;&nbsp;&nbsp;&nbsp;left: -50px;<br>
		} </p>
		<p>The same relative positioning can be accomplished with the following parameters.</p>
		<p class="code"> div { <br>
		&nbsp;&nbsp;&nbsp;&nbsp;position: relative;<br>
		&nbsp;&nbsp;&nbsp;&nbsp;top: -30px;  ##same effect as 'bottom: 30px'<br>
		&nbsp;&nbsp;&nbsp;&nbsp;right: 50px; ##same effect as "left: -50px"<br>
		} </p>
	</article>

	<article>
		<h3>Absolute Positioning, Relative To the 1st Parent Element That Has a Non-Static Positioning</h3>
		<p>Another way to move the label is to describe where you an element relative to the first parent element that has a position other than static. This sounds confusing so let's use this current webpage as an example.</p>
		<p>Right now, the first parent element that has a position that is not static is the body element. What do you think will happen to the label if we apply the following css to it?</p>

		<p class="code"> div { <br>
		&nbsp;&nbsp;&nbsp;&nbsp;position: absolute;<br>
		&nbsp;&nbsp;&nbsp;&nbsp;top: 0;<br>
		&nbsp;&nbsp;&nbsp;&nbsp;right: 0;<br>
		} </p>
		<p>Here's a hint: You will not find the label in the black canvass below. Why? Because the absolution position is relative to the first non-static parent element, the body element in this case, not the box. So the label will be at position 0 for top and right according to our absolute position coordinates in our css.  Another hint: The label is in green this time and the code should give you clues to where to look for it. You may have even seen it already.</p>
		<br>
		<div class="example"> <p id="absolute">black canvass</p><p>The label isn't in here. Look to the top right corner of the webpage.</p></div>
		<p>Be careful when applying absolute positioning. The name "absolute" belies it's true nature. Remember, absolute positioning is in relation to the nearest parent without a static positioning.</p>
	</article>

	<article>
		<h3>Fixed Positioning, Relative to the Window</h3>
		<p>Lastly, you can position a label in relation to the window itself. For example:</p>
		<p class="code"> div { <br>
		&nbsp;&nbsp;&nbsp;&nbsp;position: fixed;<br>
		&nbsp;&nbsp;&nbsp;&nbsp;bottom: 0;<br>
		&nbsp;&nbsp;&nbsp;&nbsp;left: 0;<br>
		} </p>
		<p>Again, you will not find the label near the black canvass below. Instead, you must find it in relation to the window itself. Wondering why that blue canvass label has been following you around? The preceding fixed css code is the reason.
		<br>
		<div class="example"> <p id="fixed">black canvass</p><p>Label is not in here. Look to the bottom left where the blue label is following you!</p></div>
	</article>
	</section>
	<section>
	<center>
		<h2>References</h2>
		
			<a href="http://www.barelyfitz.com/screencast/html-training/css/positioning/">BarelyFitz Designs: Learn CSS Positioning in Ten Steps</a>
			<br>
			<a href="http://www.w3schools.com/css/css_positioning.asp">W3Schools: CSS Positioning</a>
	</center>
	</section>