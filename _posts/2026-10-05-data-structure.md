---
layout: post
title: "Data Structures & Algorithms Enhancement"
date: 2026-10-05 12:00:00 -0500
categories: capstone
author: Anyka B
---

<div align="center">
    <h1>Course Catalog</h1>
</div>
<br>

<div align="left">
    <h2>Original Artifact</h2>
    <!-- Narrative Intro -->
    <p>Nine months ago, in CS 300 Data Structures and Algorithms, I created a course catalog C++ script that parsed and validated a user-provided data file, displayed the full computer science course catalog, and searched for a class by course code, displaying it if found. The script stored courses in a vector, validated and printed course information, and used a set to validate course codes and a linear search algorithm. Although the application was a solid implementation of data structures, algorithms, and performance analysis concepts for a beginner, it severely lacked structure and organization.</p>
    <!-- Original codebase link -->
    <h3>Repo</h3>
    <p> Want to see the original? Check out the repository: <a href="https://github.com/anyka-b-dril/course-catalog/tree/main/ORIGINAL_courseCatalogue">Original Course Catalog Code</a><p>
    <h2>Enhanced Artifact</h2>
    <!-- Demo video link -->
    <h3>Demo</h3>
    <!-- link charts tables and graphs -->
    <p>Check out the benchmark tests to see which of the three applications is the most efficient<a href="https://anyka-b-dril.github.io/benchmark.html">Course Catalog Benchmark</a></p>
    <br>
    <!-- Narrative continued  -->
    <p>In this enhancement, I improved the application performance by updating the underlying data structure from a vector to an unordered map, C++’s unofficial hash map. The original vector implementation required a linear search to return a single course, which checked each course sequentially to find a matching ID. While this solution works well for small data sets, lookup times grow with the dataset size, meaning ten thousand course entries could require ten thousand lookups. The hash map uses key hashing to perform lookups consistently, regardless of the catalog size. For example, a single C++ lookup in a small dataset takes a vector an average of 3 μs, while a hash map takes an average of 0.5 μs—an 83% reduction in execution time! The hash map eliminated many manual code iterations required for the loop-based linear search, reducing direct data access to a single line: catalog.find(id) or catalog.get(id). This data structure enhancement shows my awareness of complexity and my ability to identify bottlenecks and choose a more appropriate associative container.</p>
    <p>To further highlight my ability to evaluate efficiency and practicality rather than just commit to blind optimization, I also recreated the application in Java. Although rewriting the program in Java may seem unnecessary, since C++ almost always runs faster, Java might be preferred for several business, technical, and operational reasons, such as cross-platform portability, easy ecosystem integration, and faster development times. Rewriting the entire program in another programming language highlights more than my object-oriented programming skills; it shows my ability to translate C++ type values into Java object references while preserving the underlying business logic.</p>
    <p>In addition to refactoring the data structure, I created manual benchmark tests to measure execution efficiency for all three code files (C++ vector, C++ hash map, and Java hash map implementations). These benchmarks measure file parsing, sorting algorithm performance, data structure search complexity, and system-level execution across the full workflow. The tests are configured in a cloned application with the input and output actions omitted. Each benchmark routine is isolated in a method and is called from a simple benchmark entry point, making all benchmarks easy to repeat. Creating these tests highlights highly valuable skills necessary for good software engineers: resource trade-off analysis, operating system knowledge, statistical competence, and data-driven decision-making. I organized the data from these tests into several tables, bar charts, and line graphs so readers can easily compare results and spot patterns across program implementations. The visual comparison demonstrates my commitment to clear communication, attention to detail, and analytical thinking.</p>
    <p>The data structure enhancement met several course outcomes and demonstrated technical, analytical, and professional competencies. Refactoring and recreating the data structure in a different language show that I can design and evaluate computing solutions that solve a given problem using algorithmic principles, computer science practices, and standards appropriate to the solution, while managing the trade-offs involved in design choices. By creating meaningful benchmarks and charts and graphs to accompany them, I demonstrate a commitment to designing, developing, and delivering professional-quality oral, written, and visual communications that are coherent, technically sound, and appropriately adapted to specific audiences and contexts.</p>
    <p>At the start of this project enhancement, I was initially overwhelmed by creating a C++ hash map—it had been quite some time since I had coded in C++ and reviewed the manual memory-management requirements. However, after researching unordered maps, I found the implementation wasn't as complex as I thought, since unordered maps work like hash maps and don't require manual memory management under most conditions. I spent a lot of time creating the processCourseFile method. The original script opened the data file twice to extract and validate data; however, I wanted to improve this core feature as part of the data structure enhancement. I challenged myself to find a simple solution to open the file only once to make the method more efficient. Through this, I learned that setting lines is much easier in C++ than in native Java, because Java uses line-oriented input wrappers that encapsulate the input stream and don't support resetting the read pointer.</p>
    <p>I learned the most while creating the execution performance benchmarks. I had never coded benchmarks before, so creating manual tests let me explore and experiment with timing functions, measure processes, and natively shuffle data structure values. For much of the process, I was unsure how to make the benchmark tests isolated yet repeatable. The most surprising part was needing to prevent dead code elimination, where modern compilers aggressively optimize code when the result is predictable (Azad, 2025). By assigning the volatile type to a variable holding a process output, the compiler is forced not to optimize the code segment. Java also has volatile; however, it is used for multithreading synchronization, not hardware interaction.</p>
    <!-- New code link -->
    <h3>Repo</h3>
    <p> Like what you see? Check out the repository: <a href="https://github.com/anyka-b-dril/course-catalog/tree/main/Capstone_course_catalog">Enhanced Appointment Manager Code</a><p>

</div>

<div align="center">
    <h1>References</h1>
</div>

<div align="left">
    <p>Azad, L. (2025, July 25). Understanding the volatile Keyword and Compiler Optimizations. Understanding the volatile Keyword and Compiler Optimizations | by Lovekesh Azad | Medium. https://medium.com/@azad217/understanding-the-volatile-keyword-and-compiler-optimizations-22d974de9ef3</p>
    <p>Singh, R. (2024, July 30). Understand how to use Hash Map (C++) in brief. Understand how to use Hash Map (C++) in brief | by Rishabh Singh | Medium. https://medium.com/@RobuRishabh/understand-how-to-use-hash-map-c-in-brief-c119d0ca21bc </p>
    <p>Webeyez Insights Hub. (n.d.). How to Calculate Execution Time in Java: A Practical, Data-Driven Guide. How to Calculate Execution Time in Java: A Practical, Data-Driven Guide - Webeyez. https://webeyez.com/insights/guides/how-to-calculate-execution-time-in-java</p>
</div>