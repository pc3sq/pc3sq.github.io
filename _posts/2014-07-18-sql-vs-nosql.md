---
layout: post
title:  "SQL vs. NoSQL"
date:   2014-07-18
categories: technical blog
tags: week7
---
<section>
	<h2>SQL vs. NoSQL</h2>
	<article>
		<h3>Clarification</h3>
		<p>
			When we talk about the SQL versus NoSQL debate, we are really talking about relational versus non-relational databases. SQL is actually a database language used to access and query relational databases; SQL should not be used interchangeably with relational databases.
		</p>
		<p>Let's stick with relational versus non-relational from here on out.</p>
	</article>
	<article>
		<h3>What is a Relational Database?</h3>
		<p>
			A relational database stores both data and how the data relates to each other. This results is a two dimensional representation of data with each distinct entity organized in a table with columns and rows like a spreadsheet. Database languages like SQL can be used to query for information by looking for corresponding columns and rows for specific information, even joining tables with corresponding indexes, known as <i>keys</i>, for more complex queries.
		</p>

		<p>
			Furthermore, relational databases follows the principles of ACID: atomicity, consistency, isolation, durability. This ensures consistency of data in all situations of data management, sometimes at the loss of performance and scalability because of its relational and branching nature. Basically, ACID ensures that each transaction, unit of work, either completes in its entirety with all checks and balances to ensure consistency and avoid any conflict <u>OR</u> the transaction doesn't compete at all.
		</p>
	<article>
		<h3>Pros and Cons for Relational Databases</h3>
	</article>
		<p>
			When there is a clear structure to your data and you do not anticipate there being frequent changes to that structure, relational databases gives you a way to organize your information that is supported by a well-defined query language and a mature community of developers. When complex queries and analytics are foremost, relational databases are you best bet.
		<p>
			Unfortunately, as your relational database and user base grows, the constant writing to, reading from, and joining tables in your relational database will take a hefty performance beating. Adding additional hardware to bring the performance back is possible but many times not economical to do so.
		</p>
	<article>
		<h3>What are Non-Relational Databases</h3>
		<p>
			 A non-relational database eschews predefined tables in favor other ways to model data. Non-relational databases come in four major flavors:
		</p>
		<ul>
			<li>Column: Accumulo, Cassandra, HBase</li>
			<li>Document: Clusterpoint, Couchdb, Couchbase, MarkLogic, MongoDB</li>
			<li>Key-Value: Dynamo, FoundationDB, MemcacheDB, Redis, Riak, FairCom c-treeACE</li>
			<li>Graph: Allegro, Neo4J, OrientDB, Virtuoso, Stardog</li>
		</ul>
	</article>
	<article>
		<h3>Pros and Cons of Non-Relational Databases</h3>
		<p>
			Proponents of NoSQL proclaim its superior scalability and performance when compared to SQL databases. Using the BASE system (basically available, soft-state, eventually consistent), non-relational databases relax the ACID requirements that ensure consistency to achieve better availability and partitioning of data for better scalability and performance. A large part of the scability and performance gains stem from many non-relational databases storing vast amounts of data in working memory rather than relying on the constant reading and writing to disk that relational databases do. However, you lose the support of battle tested querying you get with relational databases and the community that supports them.
		</p>
		<p>
			While there are notable performance and scalability advantages to non-relational databases, they are noticeable until you begin dealing with data at the scale of what Google, Yahoo, and Facebook encounter. This leads to many developers questioning whether switching to a non-relational database offers any real advantages.
		</p>
	</article>
	<article>
		<h3>So ... Relational or Non-relational?</h3>
		<p>
			This is where knowing multiple approaches as a programmer really comes in handy. If you have a project that deals with lots of asynchronous processes, you may want to check out a dialect of LISP. But if you are dealing with modeling real world objects, you may want to use Ruby.
		</p>
		<p>
			Similarly, if you are dealing with a project that is data heavy where lots of information can be sensibly queried in tabular form, why not choose a relational database. If, on the other hand, your project deals more with the queries of information presented more like objects, you may appreciate the flexibility of not predefining your database with non-relational databases. Furthermore, non-relational databases excel at real-time analytics and there are some systems that are built in real-time that almost necessitate non-relational databases.
		</p>
		<p>
			Other considerations include which database your DBA (database administrators) prefer. If you cannot decide on one or the other, why not use each type where they make sense and then have them interact with each other?
		</p>
	</article>
</section>
<section>
	<h3>REFERENCES</h3>	
	<a href="http://www.tomsitpro.com/articles/rdbms-sql-cassandra-dba-developer,2-547-2.html">The Best of Both Worlds: Relational and NoSQL Databases</a>
	<br>
	<a href="http://www.zdnet.com/rdbms-vs-nosql-how-do-you-pick-7000020803/">RDBMS vs. NoSQL: How Do You Pick</a>
	<br>
</section>