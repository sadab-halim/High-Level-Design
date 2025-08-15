# HLD Foundations

---

## Module 1: Introduction and Core Concepts
### What is High-Level Design (HLD)?
In simple terms, **High-Level Design is the architectural blueprint of a software system**. It's the 30,000-foot view that outlines the major components of the system and how they interact with each other. It focuses on the "what," not the "how." It defines the system's structure, database design, technology stack, and communication flows between different modules.

***Analogy: Building a House***

Imagine you're building a house.

* **High-Level Design (HLD)** is the architectural blueprint. It shows the number of floors, the layout of the rooms (kitchen, bedrooms, bathrooms), where the main plumbing and electrical lines will run, and what materials will be used for the foundation and frame. It doesn't specify the brand of faucet in the bathroom or the color of the paint on the walls. It ensures the house is structurally sound, functional, and meets the owner's core needs (e.g., a family of four needs at least three bedrooms).
* **Low-Level Design (LLD)** is the detailed interior design and construction plan. It specifies the exact dimensions of each room, the type of flooring, the model of the kitchen appliances, the specific wiring diagram for each outlet, and the color codes for the paint. It's about implementing the vision laid out in the HLD.

HLD provides the skeleton; LLD adds the flesh and skin.

### **Why Was HLD Created? What Problems Does It Solve?**

In the early days of software development, developers would often jump straight into coding. For small projects, this worked. But as systems grew in complexity, this "code-first" approach led to massive problems:

1. **Lack of Scalability:** The system would work for 100 users but collapse under the weight of 10,000. There was no plan for growth.
2. **Poor Maintainability:** Without a clear structure, fixing bugs or adding new features became a nightmare. Changing one part of the code would unpredictably break another—what we call "spaghetti code."
3. **Inefficient Resource Usage:** Systems were often over-engineered or under-engineered, leading to wasted server costs or poor performance because there was no upfront analysis of the requirements.
4. **Failure to Meet Business Goals:** The final product often didn't solve the actual business problem because the technical implementation diverged from the functional requirements.

HLD was born out of necessity to solve these problems by forcing a structured, forward-thinking approach. It solves:

* **Risk Mitigation:** It identifies potential bottlenecks, single points of failure, and scalability issues before a single line of code is written.
* **Alignment:** It ensures that all stakeholders—engineers, product managers, and business leaders—are on the same page about what is being built. The HLD document serves as a contract.
* **Efficiency:** It provides a clear roadmap for the development team, preventing wasted effort and rework. It allows for better resource allocation and project planning.
* **Scalability and Performance:** It explicitly plans for future growth, ensuring the system can handle increased load and data volume over time.


#### **Core Architecture \& Philosophy**

The philosophy of HLD is rooted in a few key principles. Mastering these will fundamentally change how you approach system design.

1. **Abstraction:** HLD intentionally hides the internal implementation details of components. It focuses on the component's interface and its interactions with the rest of the system. This allows you to reason about a large system without getting bogged down in minutiae.
2. **Modularity \& Separation of Concerns:** The system is broken down into distinct, independent modules (or services), each with a specific responsibility (e.g., user authentication, payment processing, notification service). This makes the system easier to build, test, deploy, and maintain. If the payment module fails, it shouldn't bring down the user authentication module.
3. **Anticipating Change and Scale:** A good HLD is not static. It is designed for evolution. It anticipates future growth in users, data, and features. This is where concepts like load balancing, database sharding, and caching come into play—not as afterthoughts, but as part of the initial blueprint.
4. **Pragmatism and Trade-offs:** There is no "perfect" system design. Every decision involves a trade-off (e.g., choosing consistency over availability, or performance over cost). The core of HLD is to understand the business requirements deeply, identify the constraints, and make conscious, defensible trade-offs. The goal is to build a system that is "good enough" for the problem at hand, not to build a theoretical masterpiece.

***

## Module 2: The Core Curriculum - Beginner Level

This module lays the groundwork for practical HLD. We'll cover how to initiate the design process, understand what you're building, and differentiate between the high-level plan and the detailed implementation.

### 1. What is High-Level Design (HLD)?
*(Already covered in Module 1: Introduction and Core Concepts)*

As discussed, HLD is the architectural blueprint of a software system, focusing on its major components and their interactions. It defines the system's structure, database design, technology stack, and communication flows. This understanding is the absolute first step in any system design endeavor.

### 2. Difference between HLD \& LLD

Understanding the distinction between HLD and Low-Level Design (LLD) is fundamental. It defines the scope of your work at different stages of the design process.

#### **High-Level Design (HLD):**
* **Focus:** Overall system architecture, major components, and their relationships. It answers "What needs to be done?"
* **Audience:** Architects, senior engineers, product managers, and business stakeholders.
* **Details:** Less detailed. Describes the system at a conceptual level.
* **Outputs:** Architectural diagrams (e.g., block diagrams, context diagrams), component breakdown, technology choices (e.g., database type, programming language paradigm), high-level data models, API contracts (functional description).
* **Analogy:** The architect's blueprint for a house, showing rooms, walls, and main utility lines.

#### Low-Level Design (LLD):
* **Focus:** Internal logic of each component, detailed implementation, algorithms, and data structures. It answers "How will it be done?"
* **Audience:** Developers, QA engineers.
* **Details:** Highly detailed. Specifies exact classes, methods, data types, and algorithms.
* **Outputs:** Detailed class diagrams, sequence diagrams, pseudo-code, database schema (tables, columns, relationships), detailed API specifications (endpoints, request/response formats, error codes).
* **Analogy:** The detailed plans for each room, specifying furniture placement, wiring, plumbing fixtures, and exact measurements for construction.

**Why is this distinction important?**
* **Clarity of Scope:** It helps in defining responsibilities within a team. Architects focus on HLD, while developers flesh out the LLD.
* **Phased Development:** Design is an iterative process. HLD provides the guiding vision, and LLD refines it in detail for specific components.
* **Cost Efficiency:** Identifying fundamental architectural flaws in HLD is far cheaper and easier than discovering them during LLD or, worse, during implementation.


## 3. System Design Process \& Steps
Approaching system design isn't just about drawing boxes; it's a structured process. While there's no single universally mandated process, a common sequence of steps helps ensure all critical aspects are covered.

### Common System Design Process Steps:
1. **Understand Requirements (Functional \& Non-functional):** This is the most crucial first step. You cannot design a system effectively if you don't know what it needs to do and how well it needs to do it. We'll delve into this further in the next subtopic.
2. **Estimate \& Scale (Traffic Estimation \& Capacity Planning):** Based on requirements, make educated guesses about usage patterns (users, requests, data). This informs your scaling strategy.
3. **Define Core Components (High-Level Design):** Identify the main services, databases, and external systems. Draw block diagrams showing their interactions.
4. **Data Modeling:** Design the primary data structures and how they will be stored (e.g., relational, NoSQL).
5. **API Design:** Define how different components will communicate with each other (internal APIs) and how external clients will interact with the system (external APIs).
6. **Choose Technologies:** Select specific technologies based on requirements, team expertise, and industry best practices.
7. **Consider Non-Functional Aspects:** Address scalability, reliability, security, maintainability, and performance. This often involves architectural patterns like caching, load balancing, message queues, etc.
8. **Evaluate Trade-offs:** Every design decision has implications. Understand the pros and cons of different approaches.
9. **Review and Iterate:** System design is rarely a one-shot process. Get feedback, refine your design, and iterate.

**Analogy: A Chef Planning a Meal**

1. **Understand Requirements:** The chef asks, "What kind of meal do I need to prepare? (a quick snack, a family dinner, a banquet). Who am I cooking for? (dietary restrictions, preferences). How many people? When is it due?"
2. **Estimate \& Scale:** "If it's a banquet for 200, how much food do I need? How many ovens? How many staff?"
3. **Define Core Components:** "I'll need a main course, a side dish, and a dessert." (High-level menu items).
4. **Data Modeling:** "What ingredients do I need for each dish?" (List of ingredients).
5. **API Design:** "How will the main course be served with the side dish? What's the flow from kitchen to table?"
6. **Choose Technologies:** "Do I need a grill, an oven, or a slow cooker?" (Specific cooking equipment).
7. **Consider Non-Functional Aspects:** "How do I ensure the food is hot when served (performance)? How do I handle allergies (safety)? Can I prepare some parts in advance (scalability/efficiency)?"
8. **Evaluate Trade-offs:** "Do I make a complex dish that wows everyone but takes forever, or a simpler one that's quick and still tasty?"
9. **Review and Iterate:** The chef tastes, adjusts, and gets feedback.

## 4. Identifying Functional vs Non-functional Requirements
This step is critical because it forms the bedrock of your design decisions. Misunderstanding or overlooking requirements can lead to building the wrong system.

* **Functional Requirements (FRs):** These define **what the system "does."** They describe the features and behaviors that the system must exhibit. They are usually derived directly from business needs.
    * **Examples:**
        * "Users can register and log in."
        * "Customers can add items to a shopping cart."
        * "The system sends an email notification for order confirmation."
        * "Admins can manage user accounts."
* **Non-functional Requirements (NFRs):** These define **how well the system performs its functions.** They are constraints or quality attributes that the system must satisfy. These are often more challenging to define and design for.
    * **Categories of NFRs (and examples):**
        * **Performance:**
            * "The login page must load within 2 seconds for 95% of users."
            * "The API should handle 1,000 requests per second (RPS) with an average latency of 100ms."
        * **Scalability:**
            * "The system must support 1 million concurrent users."
            * "The system should be able to process 10 million transactions per day."
        * **Reliability/Availability:**
            * "The system must be available 99.99% of the time (four nines)."
            * "Data loss must not exceed 5 minutes in case of a disaster."
        * **Security:**
            * "All user passwords must be hashed and salted."
            * "The system must comply with GDPR regulations for data privacy."
        * **Maintainability:**
            * "New features should be deployable within 1 week."
            * "The system should be easily monitorable."
        * **Usability:**
            * "The user interface should be intuitive and easy to navigate."
        * **Cost:**
            * "The monthly infrastructure cost should not exceed \$10,000."

**Why distinguish them?**

* **Design Impact:** FRs dictate *what* components you need (e.g., a user service, a payment service). NFRs dictate *how* those components are built and connected (e.g., using a load balancer for performance, a highly available database for reliability).
* **Testability:** FRs are tested by checking if a feature works. NFRs are tested by stress testing, security audits, and monitoring.
* **Prioritization:** Sometimes, NFRs conflict (e.g., high security vs. high performance). Distinguishing them helps in making conscious trade-offs.

**Practical Tip:** During interviews, always clarify both functional and non-functional requirements at the very beginning. If the interviewer doesn't provide them, ask clarifying questions! This shows you understand the importance of a well-defined problem.

***

## **Module 3: The Core Curriculum - Intermediate Level**

In this module, we'll focus on estimation—the art and science of predicting the load your system will face and planning accordingly. These are not exact sciences but educated approximations that guide your architectural choices.

### 1. Traffic Estimation \& Capacity Planning
This is the umbrella term for the activities we'll discuss in this module. **Traffic Estimation** is the process of predicting how many users will access your system, what they will do, and how much data they will generate. **Capacity Planning** is the process of using those estimates to determine the resources (servers, storage, network) needed to meet performance and availability goals.

***Analogy: Planning a Supermarket***

Imagine you're opening a new supermarket.

* **Traffic Estimation:** You'd ask: How many customers will visit per day? When will the busiest hours be (e.g., after work, weekends)? What will they buy most (milk, bread vs. specialty items)? How much will each customer buy?
* **Capacity Planning:** Based on those estimates, you decide: How many checkout counters do I need? How large should the parking lot be? How much shelf space do I need for milk? How much warehouse storage is required?

Without estimation, you might build a tiny store that's perpetually overcrowded or a massive warehouse that sits empty, wasting money.

### 2. Estimating QPS, Peak Load
**Queries Per Second (QPS)**, or Requests Per Second (RPS), measures the number of requests your system receives every second. It's a fundamental metric for determining the required computational power of your application servers.

**How to Estimate QPS:**

1. **Start with Users:** The most common starting point is Daily Active Users (DAU). Let's say you're designing a simple social media feed.
    * **DAU:** 10 million
2. **Estimate User Activity:** How many requests does one user make per day? A user might open the app 5 times and scroll through 20 posts each time.
    * Requests per user per day = 5 sessions/day * 20 reads/session = 100 read requests/day.
    * Let's also assume 1% of users post something once a day.
    * Write requests = 10 million users * 1% = 100,000 write requests/day.
    * **Total Requests per Day:** (10 million users * 100 reads) + 100,000 writes = ~1 billion requests/day.
3. **Calculate Average QPS:**
    * Total seconds in a day = 24 hours * 60 min/hr * 60 sec/min = 86,400 seconds.
    * **Average QPS** = 1,000,000,000 requests / 86,400 seconds ≈ **11,500 QPS**.
4. **Calculate Peak QPS:** Traffic is never evenly distributed. A common heuristic is the **80/20 rule**: 80% of traffic comes in 20% of the time. This means traffic is much higher during peak hours. A simpler, common approach is to assume **peak load is 2x to 4x the average**.
    * **Peak QPS** = Average QPS * 2 = 11,500 * 2 = **23,000 QPS**.
    * You design your system to handle this peak load, not the average.

**Best Practices:**

* Always state your assumptions clearly. "I'm assuming 10M DAU, and each user makes 100 read requests..."
* Distinguish between read and write QPS. Read-heavy systems (like a news feed) and write-heavy systems (like a logging service) require very different architectures. In our example, the read:write ratio is 1,000,000,000:100,000 or 10,000:1.


### 3. Data Storage Growth Projection
This estimation determines how much disk space you'll need for your databases, object stores, and caches. It directly impacts cost and technology choices (e.g., can a single database handle this, or do I need a distributed system?).

**How to Estimate Storage:**

Let's continue with our social media app example. The primary data is the posts.

1. **Estimate the Size of a Single Data Unit:** What does a single post consist of?
    * `post_id`: 8 bytes (long)
    * `user_id`: 8 bytes (long)
    * `text_content`: 255 bytes (varchar)
    * `media_url`: 50 bytes (varchar)
    * `timestamp`: 8 bytes (long)
    * **Total per post (metadata):** ~329 bytes. Let's round up to **500 bytes** to account for indexing and other overhead.
2. **Estimate the Growth Rate:** We already calculated 100,000 new write requests (posts) per day.
    * **Data Growth per Day:** 100,000 posts/day * 500 bytes/post = 50 MB/day.
3. **Project for the Future:** Calculate storage needs for several years.
    * **Data Growth per Year:** 50 MB/day * 365 days/year ≈ 18.25 GB/year.
    * **Data Growth over 5 Years:** 18.25 GB/year * 5 years ≈ **91.25 GB**.
4. **Consider Media Storage:** The post metadata is small, but what about the actual media (images/videos)?
    * Assume 10% of posts have an image (average 200 KB).
    * Number of images per day = 100,000 posts * 10% = 10,000 images.
    * **Media Storage Growth per Day:** 10,000 images * 200 KB/image = 2 GB/day.
    * **Media Storage Growth over 5 Years:** 2 GB/day * 365 days * 5 years = **3.65 TB**.
5. **Factor in Replication:** For durability, you'll store multiple copies of the data. A common replication factor is 3.
    * **Total 5-Year Storage Need:** (91.25 GB + 3.65 TB) * 3 ≈ **11.2 TB**.

**Key Takeaway:** The media (stored in an object store like Amazon S3) completely dwarfs the metadata (stored in a database). This insight immediately tells you to separate your storage strategy for these two types of data.

### 4. Bandwidth Estimation
This determines the network capacity you need. It's crucial for user experience (fast load times) and cost (cloud providers charge for data egress). Bandwidth is the amount of data transferred per second.

**How to Estimate Bandwidth:**

1. **Ingress (Incoming Traffic):** Data flowing *into* your system. This is usually from user uploads.
    * From our storage calculation, we have 2 GB of images being uploaded per day.
    * **Average Ingress Bandwidth:** 2 GB / 86,400 seconds = ~23 KB/s. This is very small.
2. **Egress (Outgoing Traffic):** Data flowing *out of* your system. This is usually what users read/view.
    * We have 1 billion read requests per day. Let's assume each read is fetching the metadata and the media for one post.
    * Size of one post's data = 500 bytes (metadata) + 200 KB (image) ≈ 200.5 KB.
    * **Total Egress per Day:** 1 billion requests * 200.5 KB/request ≈ 200.5 TB/day.
    * **Average Egress Bandwidth:** 200.5 TB / 86,400 seconds = ~2.3 GB/s.
    * To convert to a more common unit (Gbps): 2.3 GB/s * 8 bits/byte = **18.4 Gbps**.
    * **Peak Egress Bandwidth** (using 2x rule): 18.4 Gbps * 2 = **36.8 Gbps**.

This egress number is significant and tells you that you need a robust network infrastructure and should probably use a Content Delivery Network (CDN) to reduce costs and latency.

### 5. Capacity Planning for Scaling

This final step brings all your estimations together to make decisions about infrastructure.

* **Application Servers (Compute):**
    * Our Peak QPS is ~23,000.
    * Let's assume a single modern server can handle 500 QPS.
    * **Number of Servers Needed:** 23,000 QPS / 500 QPS/server = **46 servers**.
    * You'd add a buffer for fault tolerance, so you might provision ~50-60 servers. This informs your decision to use an auto-scaling group.
* **Database (Storage):**
    * Our 5-year estimate for metadata is ~91 GB. This is relatively small and could fit on a single powerful database server.
    * However, our read QPS is very high. A single database might not handle the load. This leads to considering a read-replica architecture (one primary DB for writes, multiple replicas for reads) or database sharding.
* **Cache:**
    * To handle the high read volume (10,000:1 read/write ratio) and reduce database load, a cache is essential.
    * Apply the 80/20 rule: 20% of your posts generate 80% of your reads.
    * Let's cache the hot 20% of daily content.
    * **Daily Read Data:** 1 billion reads * 200.5 KB/read ≈ 200.5 TB.
    * **Cache Size:** 20% * 200.5 TB = ~40 TB. You need a distributed caching layer (like Redis or Memcached) with 40 TB of memory.
* **Network (Bandwidth):**
    * Peak egress of ~37 Gbps. This confirms the need for high-capacity load balancers and a CDN. A CDN would serve most of the media traffic, drastically reducing the load on your origin servers and saving on egress costs.

***

## **Module 4: The Core Curriculum - Advanced Level**
### 1. Understanding System Constraints
In an ideal world, we would build systems that are infinitely scalable, instantly fast, always available, completely secure, and free to operate. In the real world, we are bound by **constraints**. Constraints are the boundaries—technical, business, or physical—within which you must design your system. Recognizing and respecting these constraints is the first step toward a realistic and successful design.

***Analogy: Designing a Vehicle***

Imagine you're an automotive engineer. You can't design a single vehicle that is as fast as a Formula 1 car, as spacious as a minivan, as fuel-efficient as a scooter, and as cheap as a bicycle. The laws of physics, material science, and economics are your constraints.

* **A Formula 1 car** prioritizes speed and acceleration, sacrificing comfort, cost, and fuel efficiency.
* **A minivan** prioritizes space and safety, sacrificing speed and handling.
* The design you choose depends entirely on the problem you're solving (the "requirement"). Your job is to work within the constraints to create the best possible solution for that specific problem.

**Key Technical Constraints in System Design:**

* **Consistency, Availability, and Partition Tolerance (The CAP Theorem):** This is the most famous constraint in distributed systems. The theorem states that a distributed data store can only provide **two** of the following three guarantees:
    * **Consistency:** Every read receives the most recent write or an error. All nodes in the cluster have the same data at the same time.
    * **Availability:** Every request receives a (non-error) response, without the guarantee that it contains the most recent write. The system is always operational.
    * **Partition Tolerance:** The system continues to operate despite an arbitrary number of messages being dropped (or delayed) by the network between nodes. In modern distributed systems, network partitions are a fact of life, so **Partition Tolerance (P) is generally considered non-negotiable**.

This means you are almost always forced to choose between Consistency (C) and Availability (A).
    * **CP (Consistent and Partition-Tolerant):** If a network partition occurs, the system will shut down the non-consistent part of the system (i.e., become unavailable) to ensure that all data remains correct and consistent. *Use Case: Banking systems, e-commerce order processing. You'd rather fail a transaction than process a duplicate or incorrect one.*
    * **AP (Available and Partition-Tolerant):** If a network partition occurs, the system will remain available, but some nodes might return stale data until the partition heals. The data will eventually become consistent. *Use Case: Social media likes, view counters. It's acceptable if a 'like' count is slightly stale for a few seconds, as long as the user can still access the content.*
* **Latency vs. Throughput:**
    * **Latency:** The time it takes to complete a single request (e.g., 100ms for an API call).
    * **Throughput:** The number of requests the system can handle in a given time period (e.g., 10,000 QPS).
    * These are often in conflict. Optimizing for low latency for a single user might require dedicated resources that reduce the overall throughput. Optimizing for high throughput might involve batching requests, which increases the latency for any individual request.
* **Cost:** The monetary budget for building and operating the system. This is a universal constraint that influences every decision, from technology choices (open-source vs. managed services) to performance targets (is 99.999% availability worth 3x the cost of 99.9%?).


### 2. Trade-off Analysis Fundamentals

If constraints are the rules of the game, **trade-off analysis is how you play to win**. It is the process of consciously choosing one desirable quality at the expense of another to best meet the core requirements of the system. This is the heart of HLD. There is no right answer, only a *best* answer for a specific context.

**How to Approach Trade-off Analysis:**

A structured approach is always better than a gut feeling.

1. **Identify the Core Conflict:** State the trade-off clearly. "We need to choose between strong consistency for data integrity and lower latency for a better user experience."
2. **List the Options:** Enumerate the different architectural or technological choices available.
3. **Evaluate Pros and Cons for Each Option:** Create a table comparing the options against the critical requirements (both functional and non-functional).
4. **Make a Justified Decision:** Choose an option and explicitly state *why* you are making that trade-off, linking it back to the primary business goal.

**Example Walkthrough: Choosing a Database for a User Profile Service**

* **Requirement:** A service to store and retrieve user profile data (name, email, profile picture URL). It must be fast for reads (for displaying profiles) and highly available. Strong consistency is not a hard requirement; it's okay if a profile update takes a few seconds to propagate.
* **Core Conflict:** Do we prioritize schema flexibility and read speed (NoSQL) or the familiarity and data integrity of a relational model (SQL)?

**Trade-off Analysis Table:**


| Feature | Option A: Relational DB (e.g., PostgreSQL) | Option B: NoSQL Document DB (e.g., MongoDB) |
| :-- | :-- | :-- |
| **Consistency** | **Pro:** Strong, ACID-compliant transactions by default. High data integrity. | **Con:** Typically offers eventual consistency (weaker guarantees). |
| **Read Performance** | **Con:** Can be slower for complex joins across multiple tables. | **Pro:** Very fast reads for entire documents (user profiles). |
| **Scalability** | **Con:** Vertical scaling is common. Horizontal scaling (sharding) is complex. | **Pro:** Designed for easy horizontal scaling (sharding). |
| **Schema Flexibility** | **Con:** Rigid schema. Changes require migrations, which can be slow. | **Pro:** Flexible, schema-less design. Easy to add new fields. |
| **Availability** | Good, but often requires more complex setup for high availability (e.g., primary-standby). | **Pro:** Often has better built-in support for high availability across multiple nodes. |

**Justified Decision:**
"For the user profile service, we will choose **Option B (MongoDB)**. The primary requirements are high read performance and high availability, both of which are strengths of MongoDB. While it offers weaker consistency, this is an acceptable trade-off for this use case, as a slight delay in profile updates propagating across the system will not critically impact the user experience. The flexible schema is also a significant advantage, allowing us to easily add new profile fields in the future without complex database migrations. This aligns with our NFRs of high availability and maintainability."

---

## **Module 5: Expert - Interview Mastery**

This module synthesizes everything we've covered into a practical, interview-focused toolkit. We'll cover theoretical questions, practical design problems, and full-scale system design scenarios.

#### **Common Interview Questions (Theory)**

Here are 10-15 conceptual questions that are frequently asked in HLD interviews, along with concise, expert-level answers.

1. **Q: In your own words, what is the single most important goal of High-Level Design?**
    * **A:** The most important goal is to mitigate risk by creating a robust, scalable, and maintainable architectural blueprint *before* committing significant development resources. It ensures the system is built to meet not just immediate functional requirements, but also long-term non-functional requirements like scalability and availability.
2. **Q: When would you choose a microservices architecture over a monolith, and what's the biggest drawback of microservices?**
    * **A:** You'd choose microservices for complex systems where individual components need to be developed, deployed, and scaled independently. It's ideal for large teams and for improving fault isolation. The biggest drawback is operational complexity: you trade development simplicity for challenges in deployment, monitoring, data consistency across services, and network latency.
3. **Q: Explain the CAP theorem and give a real-world example of a system for both CP and AP.**
    * **A:** The CAP theorem states that a distributed system cannot simultaneously guarantee Consistency, Availability, and Partition Tolerance. Since network partitions are unavoidable, you must trade between Consistency and Availability.
        * **CP Example:** A banking transaction system. It will choose to become unavailable rather than process a transaction with inconsistent data, preventing issues like double-spending.
        * **AP Example:** A social media 'like' counter. The system prioritizes being available to accept the 'like' even if it means the count is temporarily out of sync across different data centers. Eventual consistency is acceptable.
4. **Q: How would you estimate the server requirements for a new service?**
    * **A:** I'd start with a "back-of-the-envelope" calculation. First, estimate Daily Active Users (DAU). Then, estimate the number of read and write requests per user per day to calculate the average QPS (Queries Per Second). I'd then model the peak QPS, often assuming it's 2-4x the average. Finally, based on a benchmark of how many QPS a single server can handle, I would divide the peak QPS by the server's capacity to get a baseline number of required servers, adding a buffer for fault tolerance and future growth.
5. **Q: What is the difference between latency and throughput?**
    * **A:** Latency is the time it takes for a single request to complete its round trip—a measure of speed. Throughput is the number of requests a system can handle in a given period—a measure of capacity. A system can have high throughput but high latency (e.g., a batch processing system). The ideal is low latency and high throughput.
6. **Q: Why is it crucial to separate functional from non-functional requirements?**
    * **A:** Because they drive different parts of the design. Functional requirements determine *what* the system does (e.g., "user can upload a photo"), which defines the components you need. Non-functional requirements determine *how well* the system does it (e.g., "uploads must complete in 2 seconds and the system must handle 1,000 simultaneous uploads"), which dictates the architecture, technology choices, and infrastructure.
7. **Q: When would you use a relational (SQL) database versus a NoSQL database?**
    * **A:** I'd use a relational database when data integrity and strong consistency (ACID transactions) are paramount, and the data has a structured, predictable schema, like in financial or e-commerce transaction systems. I'd choose a NoSQL database for use cases requiring high scalability, flexible schema, and high read/write throughput, where eventual consistency is an acceptable trade-off, such as social media feeds, IoT data, or user profiles.
8. **Q: Explain the purpose of a CDN (Content Delivery Network).**
    * **A:** A CDN is a geographically distributed network of proxy servers that cache static content like images, videos, and CSS files closer to the end-users. Its primary purposes are to reduce latency by serving content from a nearby location and to decrease the load on the origin servers, which in turn reduces egress costs and improves scalability.
9. **Q: What is a load balancer and what are some common algorithms it might use?**
    * **A:** A load balancer is a device or service that distributes incoming network traffic across multiple backend servers to ensure no single server becomes a bottleneck. Common algorithms include Round Robin (sequentially cycles through servers), Least Connections (sends traffic to the server with the fewest active connections), and IP Hash (ensures a user from a specific IP is always sent to the same server, which is useful for maintaining sessions).
10. **Q: What does it mean to design for "fault tolerance"?**
    * **A:** It means designing a system that can continue to operate, perhaps at a reduced level, even when one or more of its components fail. This is achieved through redundancy (e.g., having multiple servers, data replication), failover mechanisms (automatically switching to a standby system), and avoiding single points of failure.

## **Common Interview Questions (Practical/Coding)**

These problems test your ability to apply HLD concepts to a smaller, more focused scope.

### 1. Problem: Design a Rate Limiter
* **Task:** Implement a function `is_allowed(user_id)` that returns `true` if a user's request should be processed and `false` otherwise. The system should allow a maximum of 5 requests per user per minute.
* **Thought Process:** This is a classic problem of managing state per user. A simple and effective approach is the "token bucket" algorithm. We need a way to store the token count and the last refill time for each user. A key-value store like Redis is perfect for this due to its speed and atomic operations.
* **Ideal Solution (Python-like Pseudocode):**

```python
# We need a shared data store (like Redis) accessible by all servers.
# user_data = { user_id -> { tokens: int, last_refill_timestamp: int } }

MAX_TOKENS = 5
REFILL_RATE_SECONDS = 60 # 5 tokens per 60 seconds

def is_allowed(user_id):
    current_time = now()

    # Get user's data from Redis, or create it if it doesn't exist
    if user_id not in user_data:
        user_data[user_id] = { "tokens": MAX_TOKENS, "last_refill_timestamp": current_time }

    # Refill tokens based on elapsed time since last request
    time_elapsed = current_time - user_data[user_id]["last_refill_timestamp"]
    if time_elapsed > REFILL_RATE_SECONDS:
        user_data[user_id]["tokens"] = MAX_TOKENS
        user_data[user_id]["last_refill_timestamp"] = current_time

    # Check if user has enough tokens
    if user_data[user_id]["tokens"] > 0:
        user_data[user_id]["tokens"] -= 1
        return True # Request is allowed
    else:
        return False # Request is denied (rate limited)

```

### 2. Problem: Design a TinyURL Service's Core Logic
* **Task:** Design the core functions for a URL shortener: `shorten(long_url)` which returns a short URL, and `resolve(short_url)` which returns the original long URL.
* **Thought Process:** We need a way to map a short URL to a long URL. A hash-based approach is common, but simple hashing can lead to collisions. A more robust method is to use a counter. We can have a global counter that generates a unique integer ID for each new URL. We then convert this integer ID into a base-62 string ([a-zA-Z0-9]) to create a compact short key. We store the mapping `short_key -> long_url` in a database.
* **Ideal Solution (Python-like Pseudocode):**

```python
# Database schema: (short_key: string, long_url: string)
# A separate service or database table manages a global auto-incrementing counter.

def int_to_base62(n):
    # ... logic to convert an integer to a base-62 string ...
    # e.g., 1000 -> "gE"
    pass

def base62_to_int(s):
    # ... logic to convert a base-62 string back to an integer ...
    pass

def shorten(long_url):
    # 1. Get a new unique ID from a distributed counter service
    unique_id = get_next_unique_id()

    # 2. Convert the ID to a short key
    short_key = int_to_base62(unique_id)

    # 3. Store the mapping in the database
    database.save(short_key=short_key, long_url=long_url)

    # 4. Return the full short URL
    return "http://tiny.url/" + short_key

def resolve(short_key):
    # 1. Look up the short key in the database
    long_url = database.find_by_key(short_key)

    # 2. Return the long URL (and handle not found case)
    return long_url if long_url else "URL not found"
```

---

## System Design Scenarios

These are full, open-ended questions. The goal is to walk the interviewer through your thought process using the steps we learned.

### 1. Scenario: Design a simplified Twitter/X feed
#### Outline of a High-Level Solution:
1. **Requirements:**
        * **Functional:** Users can post tweets (text, images). Users can follow other users. Users can see a timeline of tweets from people they follow, in reverse chronological order.
        * **Non-functional:** The system must be highly available. The home timeline must load in under 200ms (low latency). The system must scale to millions of users.
2. **Estimation (assuming 100M DAU):**
        * **Write QPS:** Very low. Maybe 10M tweets/day -> ~115 QPS avg.
        * **Read QPS:** Extremely high. Each user checks their timeline multiple times a day -> Billions of reads -> ~50k-100k Peak QPS. This is a **read-heavy system**.
        * **Storage:** Text is small, but media is large. Need TBs of object storage.
3. **High-Level Architecture:**
        * **Client -> Load Balancer:** Distributes traffic.
        * **Application Servers:** Handle user requests. This is where the core logic lives.
        * **Post Service:** Handles writing new tweets to the database. When a user tweets, this service writes to a `Tweets` table and a `Followers` table.
        * **Fan-out Service (for timeline generation):** This is the key trade-off.
            * **Option A (Pull):** When a user requests their timeline, query the DB for everyone they follow, get their recent tweets, and merge/sort them. Simple, but slow for users who follow thousands of people.
            * **Option B (Push/Pre-computed):** When a user tweets, this service "fans out" the tweet to all of their followers' timeline caches. So, each user has a pre-computed timeline ready to be read. This is extremely fast for reads but complex and resource-intensive for writes (celebrity problem: one tweet creates millions of writes).
        * **Databases:**
            * `Users DB` (SQL or NoSQL): Stores user profiles.
            * `Tweets DB` (NoSQL): Stores tweet content.
            * `Followers DB` (NoSQL, graph DB): Stores follower relationships.
        * **Cache (e.g., Redis):** The core of the read-heavy architecture. Store pre-computed timelines here. `user_id -> list_of_tweet_ids`.
        * **Object Storage (S3):** For storing images and videos.
        * **CDN:** To serve media content quickly to users worldwide.
4. **Trade-offs Explained:** The most critical trade-off is choosing the **Push (Fan-out on Write)** model for timeline generation. Given the non-functional requirement of a sub-200ms timeline load and the system's 1000:1+ read-to-write ratio, optimizing for fast reads is paramount. We accept the complexity of the fan-out service to achieve this, and we'd need special handling for celebrity accounts (e.g., a hybrid model where celebrity tweets are fetched at read time).

### 2. Scenario: Design a ride-sharing service like Uber.
#### Outline of a High-Level Solution:

1. **Requirements:**
        * **Functional:** Riders can request a ride. Nearby drivers are notified. A driver accepts the ride. The rider sees the driver's real-time location.
        * **Non-functional:** High availability. Low latency for location updates (<1s). System must scale to a city-wide, then global, level.
2. **High-Level Architecture:**
        * This is a system of multiple microservices that need to communicate in real-time.
        * **Client (Rider/Driver Apps):** Communicate with the backend via APIs. Use WebSockets or MQTT for persistent connections to receive real-time updates (like driver location).
        * **API Gateway:** A single entry point for all client requests.
        * **Trip Service:** Manages the lifecycle of a ride (requested, accepted, ongoing, completed, paid). This is the state machine.
        * **Driver Location Service:** Ingests frequent location updates from driver apps. This is a **write-heavy** service.
        * **Matching Service:** The core logic. When a rider requests a trip, this service queries the Driver Location service for nearby available drivers (using a geospatial index) and then applies business logic to notify them.
        * **Notification Service:** Sends push notifications/messages to drivers and riders.
        * **Message Queue (e.g., Kafka):** The backbone of the system. Decouples the services.
            * Driver location updates are published to a Kafka topic. The Location Service consumes this.
            * Trip requests are published to another topic. The Matching Service consumes this. This makes the system resilient; if the Matching service is down, requests queue up instead of being lost.
        * **Databases:**
            * `Driver Location DB` (NoSQL like Cassandra or a DB with geospatial support like PostGIS): Optimized for high-volume writes and geospatial queries.
            * `Trip DB` (SQL or NoSQL): Stores trip data, which requires some transactional integrity.
3. **Trade-offs Explained:** The key choice is using a **message queue like Kafka** to decouple services. This sacrifices some latency compared to direct service-to-service calls but provides immense scalability and resilience. If the Matching service has a spike in requests, it can consume from the queue at its own pace. If a service goes down, messages are not lost. The choice of WebSockets/MQTT over simple HTTP polling for location updates is another trade-off, prioritizing real-time experience and efficiency over simplicity.

***
