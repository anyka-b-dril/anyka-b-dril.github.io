---
layout: post
title: "Code Review"
date: 2026-10-05 12:00:00 -0500
categories: capstone
---

<div align="center">
    <h1>Code Review</h1>
</div>

<hr>

<div align="center">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/NjldzoWIFnw?si=iViozacpH1R9PU8j" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

<div align="left">
    <h2 style="text-align: center;">Summary</h2>
    <p>Before implementing any enhancements, I conducted a comprehesive code review for each enhancement artifact. By revewing and evaluating each artifact, I can find bugs, vulnerabilities, formatting errors, and ineffciencies while refreshing my knowledge about the code base. In the video above, I review and highlight my enhancement plan over two different artifacts that I have previous created in my SNHU acedemic career: an appointment manager and course catalog.</p>
</div>

<div align="left">
    <h2 style="text-align: center;">Appointment Manager</h2>
    <h3 style="text-align: center;"> Software Design & Engineering and Databases Enhancement</h3>
    <p>Six months ago, I created the entity and logic to manage appointments (Appointment.java and AppointmentService.java), accompanied by a JUnit test suite with over 80% coverage. The entity handled appointment creation and validation, and the business logic handled initializing the appointment list and adding, deleting, and reading it. The artifact is missing a main function to run the application. Overall, the artifact is a very strong framework. The main application code is appropriately separated from the JUnit tests into two distinct folders. The main logic follows typical object-oriented programming standards and the single responsibility principle by keeping validation, getters, and setters in the same constructor file, while Service contains core business logic, such as adding and deleting an appointment.</p>
    <p>In addition not being executable, the application has some minor errors, such as:
    <ul>
        <li> The random appointment ID generation is baked into the appointment creation logic when it would be straightforward to have the generation in a separate function. </li>
        <li> Additional validation can be included to prevent mismatched input type for date and time.</li>
        <li> In AppointmentService, the celebrate success line will print whether or not the appointment is created.</li>
        <li> The variable <i>random</i> in AppointmentService should have an evident name, <i>ex randomInt</i>.</li>
    </ul>
    </p>
    <p><b>Original Artifact Architecture</b></p>
    <pre><code>/appointment-manager/
├── main
│   └── Appointment.java
│   └── AppointmentService.java
├── test
│   └── AppointmentTest.java
│   └── AppointmentServiceTest.java</code></pre></p>
</div>
<div align="left">
    <p><b>Enhancement Idea</b></p>
    <img src="https://github.com/anyka-b-dril/anyka-b-dril.github.io/blob/main/assets/img/Appointment%20Architecture%20Diagram.png", alt="New Appointment Manager Architecture Diagram">
    <p> To enhance the appointment codebase in line with software engineering and design, I will implement CRUD operations to separate business logic from data storage and prepare for a later database integration. <p>
    <ul>
        <li> Define the Appointment Repository (Interface) </li>
        <li> Implement an in-memory appointment repository <li>
        <li> Create a simple Terminal UI to make the program interactive <li>
    </ul>
</div>

<div align="left">
    <h2 style="text-align: center;">Databases: Appointment Manager</h2>
    <p>To further enhance the appointment codebase, I will integrate a MongoDB database into the application. While a HashMap is exceptionally fast, it is limited by the computer’s RAM and loses all the data when the application restarts. A database will provide data persistence, scalability, and more robust data integrity. In other words, all appointment data will be saved even after the application restarts. If a user adds new data into the system, the database enforces data integrity with schema validation.</p>
</div>

<div align="left">
    <p><b>Enhancement Idea</b></p>
    <img src="https://github.com/anyka-b-dril/anyka-b-dril.github.io/blob/main/assets/img/Appointment%20Architecture%20Diagram%20w%20Database.png", alt="New Appointment Manager Architecture Diagram">
    <ul>
        <li> Set up the database environment </li>
        <li> Implement the Mongo repository </li>
        <li> Implement Object-to-Document Helpers </li>
        <li> Verify and update JUnit testing suite </li>
    </ul>
</div>

<div align="left">
    <h2 style="text-align: center;">Algorithms & Data Structure: Course Catalog </h2>
    <p>The course catalog program reads a course catalog data file and allows users to access them intuitively through a terminal menu. After processing the data file, users can search for a course by course code (e.g., MATH201) or print all computer science courses in alphanumeric order. Each course object is stored in a vector with an average lookup time of O(logN). Although the script is functional with small datasets, the course catalog application lacks structure, organization, and effective data validation. These issues are seen in: </p>
    <ul>
        <li> In processCourseFile <i>(line 63)</i>, the method opens the data file twice, once to get a list of existing course numbers and again to create a list of existing courses</li>
        <li> Misspelled variable names</li>
        <li> Unused <code>lineNumber</code> variable in Step 1 of <code>processCourseFile</code></li>
        <li> Filepath inside of the Menu method is never used since processCourseFile asks for the filepath locally via <code>cin</code></li>
        <li> The <code>searchCourse</code> method continues to iterate through the entire course vector even if a match was found
        <li> The method<code>processCourseFile</code> uses negative logic in many spots. This contributes to a lack of else statements, which can make the code unclear</li>
        <li> More validation is needed for malformed data inputs, <i>ex improper course ID</i></li>
    </ul>
</div>

<div align="left">
    <p><b>Enhancement Idea</b></p>
    <p> Instead of using a vector, I would like to use a hash map. The hash map will provide faster average O(1) constant-time lookups compared to the vector. Although a vector is optimal for smaller data sets (as the original dataset is very small), it does not reflect a real-life use case. In the real world, colleges have hundreds of classes to choose from, so fast, predictable, and reliable lookups are essential for this solution to work.</p>
    <p>Rather than just upgrading the data structure to a hash map in C++, I would like to also create the application in Java, which has a built-in hash map as part of its core framework. Even though C++ is generally considered faster than Java when executing data algorithms, as C++ compiles directly into machine code, Java may be chosen over C++ in a professional setting due to several business, technical, and operational reasons. By using the two different languages, I can evaluate the application across two distinct dimensions: algorithmic complexity and language runtime architecture. Through the use of benchmarks, I plan to compare each solution within these categories:</p>
    <ul>
        <li> File read and parse time </li>
        <li> Sorting time </li>
        <li> Key-value lookup time </li>
        <li> Memory mangement  </li>
    </ul>
</div>
