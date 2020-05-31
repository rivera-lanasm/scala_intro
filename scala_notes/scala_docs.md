## Resources of Scala

#### Guides:
1. [Alvin Alexander's hello-scala](https://hello-scala.com/)
2. [Scala best practices](https://nrinaudo.github.io/scala-best-practices/)
3. [Scala exercises](https://www.scala-exercises.org/)


#### Misc. 
1. How Scala’s source code is interpreted by the compiler to produce efficient and effective [JVM bytecode](https://www.toptal.com/scala/scala-bytecode-and-the-jvm)
  - Brief overview of some major elements of the Java Virtual Machine architecture, class file structure, and assembler basics.
  - decompiling class files with javap
  - Constant pool, field and method table
  - javap; translates bytecode into human readable form --> javap -p -c RegularPolygon.class
  - methods in class file organized in call stack, each compiled as a stack frame (operand stack and local variable frame)
2. [Scala Internals](https://medium.com/@alessandroheres/scala-internals-and-intermediates-483e654bb6d2)
  - how JVM implements the Scala functions 
3. [Sealed Traits](https://underscore.io/blog/posts/2015/06/02/everything-about-sealed.html)
  - algebraic data types --> a complex definition is just an algebraic data type — it is defined entirely in terms of ands and ors.
4. [Re-learn SBT](https://kubuszok.com/2018/relearn-your-sbt/)
  - naming each .sbt file build.sbt in a multimodule project a cargo-cult programming. If you give each of these files a meaningful name, it will be easier to fast-navigate, or pinpoint which file errored on sbt start
  - leave the build.sbt name for our root project
  -  version.sbt file which only contains version := "value" makes it easier to do a version bump programmatically
5. [Understanding SBT](http://www.beyondthelines.net/computing/understanding-sbt/)
  - written in plain scala, so must be compiled --> build.sbt
6. [Option/Some/None Pattern](https://alvinalexander.com/scala/best-practice-option-some-none-pattern-scala-idioms/)
  - Option is a collection with zero or one elements
  - access values in Option with 1) getOrElse 2) foreach 3) match expr
  - working with collections, bag.map(toInt).flatten, or, bag.map(toInt).collect{case Some(i) => i}


#### FP
1. [What FP is all about](https://www.lihaoyi.com/post/WhatsFunctionalProgrammingAllAbout.html)
  - imperative paradigm issues: 
    - there is an ordering of steps, but the ordering between only some is required
    - instructions are based on changing the state of things, but evidence of this is hidden
    - dependencies become difficult to track 
  - core of Functional Programming is thinking about data-flow rather than control-flow
  - what really matters is the shape of the data-flow graph, we can freely re-arrange the statements in the code, and the order of execution, as long as the graph shape is preserved


#### Other
- https://medium.com/@bfortuner/python-multithreading-vs-multiprocessing-73072ce5600b
- https://medium.com/mop-developers/parallel-computing-in-python-and-scala-37d3561b4c08
- https://www.lihaoyi.com/post/EasyParallelProgrammingwithScalaFutures.html
- https://www.lihaoyi.com/post/HowtoworkwithSubprocessesinScala.html
- https://jobs.zalando.com/en/tech/blog/parallel-computing-with-scala/?gh_src=4n3gxh1%3Fgh_src%3D4n3gxh1
- https://stackoverflow.com/questions/231767/what-does-the-yield-keyword-do
- 
