## [Introduction][1]
- "System Design in a Hurry" aims to help candidates prepare efficiently for system design interviews: provide the 20% of topics that yield 80% of the benefits.

### Interview Types
- Product Design (most common): Focus on user requirements and high-level design.
- Infrastructure Design (less common): Design a backend system that supports a particular infrastructure use case. Ex: design a message broker or rate-limiter.
- Object Oriented Design (less common): Detail class structures and relationships. These interviews are more common at companies using Java, like Amazon. Ex: design a parking lot system or vending machine. Use [Grokking...][3] to study for this.
- Frontend Design - Ex: design the frontend architecture for a spreadsheet app or video editor. Use [greatfrontend.com][2] to study for this.

### Interview Assessment
- The most common reason to fail is not delivering a working system, often because of a lack of structure in the candidate's approach.
- As your level increases, more of the interview will be spent going in-depth on individual components.

#### Problem Navigation
- You should be able to break down the problem into smaller, more manageable pieces, prioritize the most important ones, and then navigate through those pieces to a solution.
- Most common failings:
   - Insufficient requirement-gathering.
   - Not focusing on the most-important aspects of the problem.
   - Getting stuck on a piece of the problem and not moving forward.

#### High-Level Design
- You should be able to describe how you would solve each piece of the problem, and how those pieces fit together into a cohesive whole.
- Most common failings:
   - Not having enough understanding of core concepts.
   - Ignoring scaling/performance considerations.
   - Spaghetti design.

#### Technical Excellence
- You should know about best practices, current technologies, and how to apply them.
- Most common failings:
   - Not knowing about current tech.
   - Not knowing how to apply that tech to the problem.
   - Not knowing common patterns / best practices.

#### Communication & Collaboration
- You should be able to communicate complex concepts, respond to feedback and questions, and in some cases work together with the interviewer.
- Common failings:
   - Not being able to communicate clearly.
   - Being defensive / argumentative.
   - "Getting lost in the weeds".

## [Delivery Framework][4]
- The most common reason mid-level candidates fail is that they fail to deliver a working system in the allotted time.
- Here we present a structured approach to system design interviews aimed at delivering a working system in 45 minutes.

### Requirements (~5 minutes)
- We recommend you break up requirements into two sections: functional and non-functional requirements.
- **Functional Requirements**: "Users/Clients should be able to..." statements. The real system may have hundreds of features; you should identify and prioritize the top 3.
- **Non-functional Requirements**: "The system should be (able to)..." statements. Availability vs. consistency, scale, latency, durability, reliability, etc.
   - The most important thing is to identify what makes this system uniquely challenging.
   - Be specific about numbers: "latency under 100ms" vs. "it should be fast".
   - Capacity Estimation: Explain to the interviewer that you would like to skip on estimations upfront and that you will do math while designing when/if necessary. Perform calculations only if they influence design.
      - Ex: Can you use a single instance of a min-heap to calculate the top trending FB posts or will you need to shard it across multiple instances?

### Core Entities (~2 minutes)
List and define core entities relevant to the system.

### API or System Interface (~5 minutes)
Define the contract between the system and its users, typically through RESTful or GraphQL APIs.

### Data Flow (~5 minutes, optional)
Describe the high-level sequence of actions for backend systems.

### High Level Design (~10-15 minutes)
Design the architecture using components like servers and databases, focusing on meeting functional requirements first.

### Deep Dives (~10 minutes)
Iterate and harden the design to meet non-functional requirements, address edge cases, and improve based on feedback.


[1]: https://www.hellointerview.com/learn/system-design/in-a-hurry/introduction
[2]: https://www.greatfrontend.com/
[3]: https://www.educative.io/courses/grokking-the-low-level-design-interview-using-ood-principles
[4]: https://www.hellointerview.com/learn/system-design/in-a-hurry/delivery

