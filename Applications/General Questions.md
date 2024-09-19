What is clean code to you? General
what if someone tells you there's a deadline that you cannot do all that? Compromise 
How do you ensure your code is tested?
Pros and Cons of Mockito?

they want to bring it to the wider commercial market - its applicable t sports betting how can we apply it oto the wider commercial market
#### Tell me about yourself?
my name is bruna and 
i went to university in sout bank university for mechanical engineering. i graduted with a first clas
I hold a 1st Class Master’s degree in Mechanical Engineering, graduating at the top of my class and with the highest grade in my final year project. During university, I discovered my passion for coding in a robotics module, which inspired me to pursue a career in software development. To transition into tech, I completed an intensive bootcamp, where I gained experience building RESTful APIs with Java and Spring, managing relational databases using SQL, and developing front-end applications with JavaScript and React, and containerization using Docker. Following this, I joined the graduate scheme at FSB Technology Ltd, a sports betting and casino company. There, I applied these technologies throughout the full software development lifecycle, working on both the front end and back end. My responsibilities included designing, implementing, and maintaining code, participating in Agile practices like sprint planning, code reviews, documentation, and testing. I also contributed to support tasks, resolving high-priority bugs, and took part in releases.

A key part of my role involved collaborating with stakeholders, product teams, QA, and fellow engineers to ensure knowledge sharing and find the best solutions to issues. As I near the end of my graduate scheme, I’m looking for an opportunity where I can work with more modern technologies and more modern pratcices. Specifically, I’d like to expand my experience in DevOps, learning tools like Docker, Kubernetes, and cloud technologies. I believe that embracing a DevOps mindset, with its focus on continuous integration and deployment, is key for a developer to allow us to develop production ready code, to ship code off faster to receive feedback and work on iterations of the solution.

### Why do you want to work for us?

The Workshop stands out to me because of its work in the sports betting and casino space—an industry where I have direct experience and have thoroughly enjoyed working. This field has provided me with valuable business insights and highlighted its significant growth potential. There is considerable global demand for technical services that deliver innovative sports betting solutions, making it a sector I am eager to continue in.

This role excites me because it merges my industry experience with the chance to delve into the fintech world. Venturing into fintech aligns with my career aspirations, as finance is integral to our global economy. Financial systems impact virtually every industry, and fintech is crucial for advancing and building a global economy.

What makes this opportunity particularly appealing is the focus on blockchain technology. Blockchain offers substantial benefits to the sports betting industry, particularly with its immutable nature, which ensures secure transaction tracking. The potential of blockchain extends well beyond sports betting, and I am impressed by The Workshop’s commitment to leveraging blockchain and expanding its solutions to a wider audience.
#### What interests you about the financial industry?

The financial industry fascinates me for several reasons. Firstly, it's at the heart of our global economy; financial systems and the decisions made within them ripple out to impact virtually every other industry. Understanding these complex, interconnected systems can provide fascinating insights into not just the economy but also social and geopolitical trends.

Secondly, the constant evolution and innovation in the finance industry keep it challenging and intellectually stimulating. Whether it's the emerging trends in fintech, the increasing emphasis on sustainability and ESG investing, or the exciting developments around cryptocurrencies and blockchain technology, there is always something new to learn and understand.

Lastly, a career in finance offers the opportunity to make a tangible difference - from helping individuals plan their financial future, aiding businesses in making strategic decisions, to supporting economic growth and development. The role that the finance industry plays in shaping our communities and our future is of significant interest to me.

### What do you think you bring to the company?

I bring valuable experience from the sports betting and casino industry, where I’ve worked directly with businesses providing sports betting solutions. This background allows me to apply both my practical knowledge and business logic effectively. My genuine passion for creating impactful user experiences is evident from my previous role, where I saw firsthand the positive effects of well-designed solutions.

I possess a strong growth mindset and am committed to continuous learning and excellence. My proactive approach is reflected in my past experiences, such as working on complex projects like decoupling our sportsbook from account management. In that project, I integrate a third-party account management system, utilizing Test-Driven Development principles with JUnit and Mockito. This effort played a key role in retaining a major business partnership, demonstrating the tangible impact of my contributions.

Collaboration is central to my work ethos. I strongly believe in knowledge sharing and have actively promoted practices like pair programming to onboard new team members and share code structure and business logic. In my most recent project, which involved transitioning to an event-driven architecture using ActiveMQ and MongoDB, I proactively engaged with engineers and the product team to understand requirements and achieve our goals. This project, which included consolidating multiple third-party sports data feeds into a single feed, significantly reduced company expenditure.


-> maybe saying too much try condense mor like tell less stories. maybe just say specifically what would make me stand out
- i have sportsbetting experience
- my engineering manager vouches for my collaboration
- my team mates ovuhc for my growth mindset and proactives

### Overview of my skills
I have experience working on both the **backend** and **frontend** sides of software development.

On the **backend**, I have developed, maintained, and tested **RESTful applications** using **Java, Spring**, and **PostgreSQL**. A notable project involved separating our sportsbook from the personal account management system, where I implemented an API to enable integration with third-party account management systems. I follow a **test-driven development (TDD)** approach, using **JUnit** and **Mockito** for testing.

Additionally, I have worked with **event-driven architecture** and messaging systems such as **ActiveMQ**. In my most recent project, I built a market and pricing analysis system, which leveraged ActiveMQ for communication between different applications. I also utilized **MongoDB** to store and analyze the data feeds.

For version control, I used **Git**, and for CI/CD pipelines, I relied on **Jenkins**. I also incorporated **Datadog** for production log monitoring.

On the **frontend**, I have experience with **JavaScript, React, CSS,** and **HTML** to create features based on **Figma** designs and change requests. One of my key frontend projects involved eliminating memory leaks in a React application, which reduced memory usage and significantly improved the initial load time of our login app.

I regularly collaborate with global cross-functional teams, participating in **Agile practices** like daily standups, pair programming, code reviews, and writing documentation.

### How do you ensure your code is well tested?
Firstly, when I have a new feature to implement, I take a **BDD (Behavior-Driven Development)** approach. This involves converting feature requirements into Gherkin syntax, which helps me better understand both the requirements and the functionality I need to produce. I also take part in **3 Amigos meetings**, where we collaborate to align on the feature. This process also helps me identify potential edge cases, such as handling incorrect user inputs.

Once I start coding, I follow a **TDD (Test-Driven Development)** approach. I write tests before implementing the functionality, which guides the development and ensures the code meets the expected behavior. Afterward, I refactor the code to maintain cleanliness and efficiency.

I focus on **three types of testing**:
1. **Unit testing**: I isolate specific units to ensure they work independently. I prefer using **JUnit** and **Mockito** for this. Mockito allows me to mock dependencies, ensuring I’m testing individual methods in isolation, not the entire feature.
2. **Integration testing**: This involves testing how my logic interacts with other parts of the application. For example, using `@DataJpaTest` to ensure proper repository-database interactions, or `@SpringBootTest` to load the full Spring application context. I also use slice annotations like `@WebMvcTest` to test specific layers with only the required beans.
3. **End-to-end testing**: I use the **Postman test suite** to define and automate requests in sequence, testing both success and failure scenarios based on Gherkin scripts. This allows me to cover scenarios without manually calling endpoints. I also use **Swagger UI** or manually navigate the website to test from the user’s perspective.
4. 
Before committing code, I run all tests and build the project using **Maven** to ensure it’s production-ready. These tests—written using JUnit, Mockito, and Spring—are integrated into the **CI/CD pipeline**. This ensures that all functionality works correctly before deployment.

## What do you consider clean code?
**Clean code** is code that is easy to understand, maintain, and extend. It adheres to certain principles and practices that help developers write high-quality software. The main characteristics of clean code include:

1. **Readability and Simplicity**: Clean code is written in a way that other developers can easily understand. This involves:
    - Using meaningful and relevant variable, method, and class names.
    - Keeping methods and functions short and focused on doing one thing well.

1. **Maintainability**: Clean code is easy to maintain and update over time. It avoids unnecessary complexity, making it simple for developers to fix bugs or add new features without breaking existing functionality.
    
3. **Well-Organized**: Clean code follows proper structure and organization, making it intuitive to follow the flow of logic. It breaks down problems into smaller, manageable pieces rather than combining multiple responsibilities into a single function or class.
    
4. **DRY (Don’t Repeat Yourself)**: Clean code avoids redundancy. The **DRY principle** encourages eliminating duplicated code by ensuring that any piece of functionality is written only once and reused across the codebase.
    
5. **Single Responsibility Principle**: Each class, function, or method should have only one responsibility, making the code more modular and easier to manage.
    
6. **Loose Coupling**: Clean code ensures that different parts of the application are loosely coupled. This means minimizing dependencies between modules or classes to make them more flexible and easier to change or extend.
    
7. **Correct Error Handling**: Clean code anticipates potential errors and handles them appropriately. Good error handling ensures that the program can gracefully recover or notify users without crashing.
    
8. **Testability**: Clean code is thoroughly tested, usually by applying practices like **TDD (Test-Driven Development)**. Code that has good test coverage is more reliable and easier to modify without introducing bugs.
    
9. **OOP Principles**: Clean code often leverages **Object-Oriented Programming (OOP) principles** such as:
    
    - **Inheritance**: Avoiding code duplication by creating shared behaviour in parent classes.
    - **Polymorphism**: Simplifying complex conditional logic by using dynamic method calls.

In summary, clean code not only works correctly but is also efficient, easy to understand, and easy to modify. Following best practices like DRY, single responsibility, and loose coupling helps ensure the codebase is scalable and adaptable over time.

## How do you react to stressful situations?
**Stress is a normal reaction to challenging situations, and for me, the key to handling stress is to stay positive and focus on what I can control. I accept that there are some things beyond my control, and I focus on maintaining healthy habits such as proper planning, time management, and open communication with my team.**

**For example, when I first joined FSB, I was assigned to build a frontend application from scratch, translating Figma designs into a dynamic web page. This was my first project that wasn’t related to bug fixing, and I hadn’t yet worked extensively with CSS. Naturally, I felt stressed because I knew it would be challenging.**

**To manage this stress, I implemented several strategies:**

1. **Time Management:** I broke down the project into smaller, manageable tasks. This helped me stay organized and prevented the overall project from feeling overwhelming. I set milestones for each component of the web page, which allowed me to track my progress and stay on schedule.
    
2. **Seeking Support:** I communicated with other developers on my team to get their professional opinions and guidance on how to tackle specific aspects of the project. This helped me gain confidence and clarity on the technical approach I should take.
    
3. **Feedback and Iteration:** After completing the initial version of the application, I proactively sought feedback from my colleagues during code reviews. I took their suggestions to heart and refactored my code, which ultimately improved the quality of the project.
    

**As a result, I successfully delivered the project on time and received positive feedback from my team for writing clean and high-quality code. This experience taught me that breaking down a complex task and maintaining open communication are essential strategies for handling stress effectively.**
## What is an occasion where you thought you excelled in a complex task?
Recently, I had to investigate an issue on our production servers that was causing duplicate payments. At first glance, it seemed straightforward because it involved a third-party payment processor. However, after thorough investigation—recreating the issue in a controlled environment, examining logs, and liaising with the third party—I realized the bug was actually a concurrency issue within our own application.

What made this task particularly complex was my limited experience with concurrency and thread safety at the time, and the lack of detailed server logs. The logs only showed that the payment endpoint was being called, but not why it was happening twice, milliseconds apart.

To tackle this, I added detailed logs to the relevant sections of the code, allowing me to pinpoint the exact sequence of events. This confirmed that the issue was due to concurrent requests leading to the application pulling incorrect data from the database before the previous thread had finished executing. After researching best practices for handling concurrency and considering several potential solutions, I decided to implement a database lock. This ensured that data integrity was maintained by preventing multiple threads from accessing and modifying the data simultaneously.

As a result, I not only resolved the duplicate payment issue but also gained a deeper understanding of concurrency and thread safety, which I’ve since applied to other projects. This experience helped me grow as an engineer and demonstrated my ability to navigate and solve complex problems effectively.
## Example of solving problem

**Example of Problem Solving:**

**Situation:**  
In my previous role at FSB, I was tasked with resolving a critical issue where users were experiencing duplicate payments on our platform. This was a high-priority issue as it impacted customer trust and had financial implications for the business.

**Task:**  
My responsibility was to investigate the root cause, implement a solution, and ensure the issue was resolved without introducing new problems into the payment flow. The challenge was that this issue seemed related to a third-party payment processor, and I had limited visibility into their systems. Additionally, I had minimal experience with concurrency issues, which I suspected might be a contributing factor.

**Action:**  
I started by thoroughly analyzing the logs and recreating the issue in a controlled environment. After confirming it was a concurrency issue within our application, I realized that multiple payment requests were being processed simultaneously, leading to data inconsistencies.

1. **Research & Diagnosis:** I researched concurrency issues, focusing on thread safety and database operations. I also consulted with senior developers to gain insights into potential solutions.
2. **Implementation:** I added detailed logging to critical sections of the code to track the execution flow and pinpoint where the problem was occurring. Once I identified the issue, I implemented a database locking mechanism to prevent multiple threads from accessing and modifying the same data concurrently.
3. **Testing:** I conducted rigorous testing in a staging environment to ensure the solution worked under various conditions and did not introduce new issues.

**Result:**  
The solution successfully resolved the duplicate payment issue, restoring data integrity and preventing financial discrepancies. As a result, customer complaints decreased significantly, and the business regained trust in the payment process. My manager and colleagues appreciated my methodical approach to identifying and resolving the issue, which also deepened my understanding of concurrency and thread safety.

## CI/CD question

## What is kubernetes? What is a pod?

## Difference between Spring and Spring Boot

## Advantages of spring

## Hibernate




Look at the technologies:
- cassandra
- docker
- kubernetes
- elasticsearch
- postgresql
- rabbitMQ
- Angular



* Clean Code and Quality Code;
* Full software development cycle;
* Testing Pyramid;
* Continuous Learning and an open mind to learn, always;
* Collaboration;
* Agile Methodologies;
* TDD approach;
* CI/CD pipelines;
* DevOps mindset.