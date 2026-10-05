---
layout: post
title: "Software Design & Engineering Enhancement"
date: 2026-10-06 12:00:00 -0500
categories: capstone
---

<div align="center">
    <h1>Appointment Manager</h1>
</div>

<div align="left">
    <h1>Original Artifact</h1>
    <hr>
    <p>Six months ago, I created the entity and logic to manage appointments (Appointment.java and AppointmentService.java), accompanied by a JUnit test suite with over 80% coverage. The entity handled appointment creation and validation, and the business logic handled initializing the appointment list and adding, deleting, and reading it. At the time, the appointment manager had no application logic, which made it a strong, portable framework—a malleable piece of clay waiting to be shaped and fired into a technical stack.</p>
</div>

<div align="left">
    <h1>Enhanced Artifact</h1>
    <hr>
    <p>From a flat four-file script, I upgraded the appointment manager’s structure to a Model-View-Controller design pattern. Instead of only having a data model and business logic, I developed an interface and an in-memory data repository utilizing a hash map. The hash map simulates a database and demonstrates my understanding of data structures, data persistence, abstraction, and state management. Furthermore, I refined the data actions to mirror typical CRUD operations, such as a find-by-ID method. Improving the service component to use standard data lifecycle methods demonstrates the implementation of core business rules, validation logic, and data transformation. By decoupling business logic from data storage, each modular system has a separate, explicit job, making it easier to test, maintain, and adapt the application over time. Future developments, such as storage engine migration and adding other interface components, can plug in cleanly without expensive codebase refactoring.</p>
    <p>The test suite is organized under a matching package hierarchy, utilizing JUnit 5 to strategically test the repository, state isolation, service validation rules, and boundary conditions. Additionally, I made the appointment manager executable by creating a terminal view with a dedicated entry point in the standalone Main class. The user interface includes a controlled menu that lets users enter a number to perform data operations. The interface features robust error handling so that invalid input entries trigger feedback rather than crashing the entire application. With these improvements successfully implemented, my outcome-coverage plan remains on track. The next database enhancement to this application will replace the in-memory repository with a native MongoDB implementation to meet persistence outcomes.</p>
    <p>With this enhancement, I met several course outcomes outlined at the beginning of the course. Using an in-memory hash map to simulate a database and separate data storage from the application logic aligns well with designing and evaluating computing solutions that use standard practices while managing trade-offs. The in-memory repository shows attention to trade-offs by preventing early dependence on external sources while also showing clear motivation to further improve service independence. Refactoring the application from direct data access to a standard repository pattern with CRUD operations reflects modern computing practices, giving the application a professional backend structure that can be easily expanded upon. This enhancement aligns with using well-founded, innovative techniques, skills, and tools to implement computer solutions that deliver value and accomplish industry-specific goals. Lastly, decoupling the architecture, updating data operations, and maintaining JUnit tests show a commitment to a security mindset to reduce vulnerabilities, address design flaws, and protect the privacy and security of data and resources.</p>
    <p>While modifying and enhancing the artifact, I learned how to create a pure Java interface. I have created other interfaces to use databases in the past, but I have not created an interface to use my own data structure. The interface will make the application easier to maintain, and I will be able to switch between different data structures easily. The most challenging part of the enhancement was refactoring the appointment service file—I felt like I had rewritten the entire file from scratch. Although almost all of the logic was the same, I struggled to extract IDs and dates from appointment objects under the new data abstraction. Even though I spent a lot of time thinking about how to simplify or make each line more efficient, I overthought some validation loops. I wrote many unreachable loops intended to validate user input, not the data itself.</p>
</div>