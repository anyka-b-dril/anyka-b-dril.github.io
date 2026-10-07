---
layout: post
title: "Software Design & Engineering Enhancement"
date: 2026-10-05 12:00:00 -0500
categories: capstone
author: Anyka B
excerpt: "The Blueprint Upgrade: How I Rewrote My Appointment Manager’s Architecture"
---

<div align="center">
    <h1>Appointment Manager</h1>
</div>
<br>

<div align="left">
    <h2>Original Artifact</h2>
    <!-- Narrative Intro -->
    <hr>
    <p>Six months ago, I created the entity and logic to manage appointments (Appointment.java and AppointmentService.java), accompanied by a JUnit test suite with over 80% coverage. The entity handled appointment creation and validation, and the business logic handled initializing the appointment list and adding, deleting, and reading it. At the time, the appointment manager had no application logic, which made it a strong, portable framework—a malleable piece of clay waiting to be shaped and fired into a technical stack.</p>
    <h3>Original Architecture</h3>
    <!-- Code block -->
    <pre><code>/appointment-manager/
├── main
│   └── Appointment.java
│   └── AppointmentService.java
├── test
│   └── AppointmentTest.java
│   └── AppointmentServiceTest.java</code></pre>
    <!-- Original codebase link -->
    <h3>Repo</h3>
    <p> Want to see more? Check out the repository: <a href="https://github.com/anyka-b-dril/appointment-manager-architecture/tree/main/ORIGINAL_appointment_manager">Original Appointment Manager Code</a><p>

</div>

<div align="left">
    <h2>Enhanced Artifact</h2>
    <hr>
    <h3>Enhanced Architecture</h3>
    <!-- Code block -->
    <pre><code>/appointment-manager/
├── src/main/java/
|   └── com.sparks.sparklink
|       └── Main.java
|       └── model
|       |   └── Appointment.java
|       └── repository
|       |   └── AppointmentRepository.java
|       |   └── InMemoryAppointmentRepo.java
|       └── service
|       |   └── AppointmentService.java
|       └── view
|           └── AppointmentManager.java
├── src/test/java/
|   └── com.sparks.sparklink
|       └── model
|       |   └── AppointmentTest.java
|       └── service
|           └── AppointmentServiceTest.java
└── pom.xml</code></pre>
    <!-- Demo video link -->
    <h3>Demo</h3>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/PsAYmqhff10?si=Dr0WN6-SXIrvO1nt" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
    <br>
    <!-- Narrative continued  -->
    <p>From a flat four-file script, I upgraded the appointment manager’s structure to a Model-View-Controller design pattern. Instead of only having a data model and business logic, I developed an interface and an in-memory data repository utilizing a hash map. The hash map simulates a database and demonstrates my understanding of data structures, data persistence, abstraction, and state management. Furthermore, I refined the data actions to mirror typical CRUD operations, such as a find-by-ID method. Improving the service component to use standard data lifecycle methods demonstrates the implementation of core business rules, validation logic, and data transformation. By decoupling business logic from data storage, each modular system has a separate, explicit job, making it easier to test, maintain, and adapt the application over time. Future developments, such as storage engine migration and adding other interface components, can plug in cleanly without expensive codebase refactoring.</p>
    <p>The test suite is organized under a matching package hierarchy, utilizing JUnit 5 to strategically test the repository, state isolation, service validation rules, and boundary conditions. To run tests upon building the project, I added the Surefire Maven plugin. Additionally, I made the appointment manager executable by creating a terminal view with a dedicated entry point in the standalone Main class. The user interface includes a controlled menu that lets users enter a number to perform data operations. The interface features robust error handling so that invalid input entries trigger feedback rather than crashing the entire application. With these improvements successfully implemented, my outcome-coverage plan remains on track. The next database enhancement to this application will replace the in-memory repository with a native MongoDB implementation to meet persistence outcomes.</p>
    <p>With this enhancement, I met several course outcomes outlined at the beginning of the course. Using an in-memory hash map to simulate a database and separate data storage from the application logic aligns well with designing and evaluating computing solutions that use standard practices while managing trade-offs. The in-memory repository shows attention to trade-offs by preventing early dependence on external sources while also showing clear motivation to further improve service independence. Refactoring the application from direct data access to a standard repository pattern with CRUD operations reflects modern computing practices, giving the application a professional backend structure that can be easily expanded upon. This enhancement aligns with using well-founded, innovative techniques, skills, and tools to implement computer solutions that deliver value and accomplish industry-specific goals. Lastly, decoupling the architecture, updating data operations, and maintaining JUnit tests show a commitment to a security mindset to reduce vulnerabilities, address design flaws, and protect the privacy and security of data and resources.</p>
    <p>While modifying and enhancing the artifact, I learned how to create a pure Java interface. I have created other interfaces to use databases in the past, but I have not created an interface to use my own data structure. The interface will make the application easier to maintain, and I will be able to switch between different data structures easily. The most challenging part of the enhancement was refactoring the appointment service file—I felt like I had rewritten the entire file from scratch. Although almost all of the logic was the same, I struggled to extract IDs and dates from appointment objects under the new data abstraction.</p>
    <p>Even though I spent a lot of time thinking about how to simplify or make each line more efficient, I overthought some validation loops. I wrote many unreachable loops intended to validate user input, not the data itself. Likewise, I changed the order of the data validation code inside the entity validation functions. I originally thought I was improving it by ordering each check by occurrence frequency; instead, I created null pointer and illegal argument exceptions, which my JUnit tests luckily caught.</p>
    <p>Lastly, my project wasn't configured to run JUnit tests automatically. The project architecture was misconfigured; instead of having a src/main/java and src/test/java path, the main and test folders were at the same directory level as src. This small mistake made it impossible for Maven to find and run the unit tests under the Surefire Maven plugin. Ultimately, I had two choices: fix the path structure or configure the build path explicitly. I decided to continue fixing the file structure to stay consistent and retain native tooling support.</p>
    <!-- New code link -->
    <h3>Repo</h3>
    <p> Like what you see? Check out the repository: <a href="https://github.com/anyka-b-dril/appointment-manager-architecture/tree/main/Capstone_AppointmentManager">Enhanced Appointment Manager Code</a><p>

</div>