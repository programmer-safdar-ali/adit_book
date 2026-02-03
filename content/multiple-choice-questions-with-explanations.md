# Multiple Choice Questions (MCQs) with Detailed Explanations

## Chapter 1: Core Networking Fundamentals

### Question 1
Which of the following network topologies has a single point of failure that can bring down the entire network?
A) Mesh
B) Star
C) Ring
D) Bus

**Answer: D) Bus**

**Explanation:** In a bus topology, all devices share a single communication line (bus). If this bus fails, the entire network goes down. In contrast, mesh topology has multiple paths, star topology has a central hub that can be redundant, and ring topology can be designed with redundancy to prevent complete failure.

### Question 2
What is the primary function of the Network Layer (Layer 3) in the OSI model?
A) Physical signal transmission
B) Routing and logical addressing
C) Error detection and correction
D) Session establishment

**Answer: B) Routing and logical addressing**

**Explanation:** The Network Layer (Layer 3) is responsible for routing data between different networks and handling logical addressing (IP addresses). It determines the best path for data to travel across networks and handles packet forwarding between different network segments.

### Question 3
Which subnet mask would be used for a /27 network?
A) 255.255.255.0
B) 255.255.255.128
C) 255.255.255.192
D) 255.255.255.224

**Answer: D) 255.255.255.224**

**Explanation:** A /27 network means 27 bits are used for the network portion, leaving 5 bits for hosts. In binary, this is 11111111.11111111.11111111.11100000, which translates to 255.255.255.224 in decimal.

### Question 4
Which routing protocol is classified as a distance vector protocol?
A) OSPF
B) IS-IS
C) RIP
D) EIGRP

**Answer: C) RIP**

**Explanation:** RIP (Routing Information Protocol) is a distance vector protocol that uses hop count as its metric. OSPF and IS-IS are link-state protocols, while EIGRP is a hybrid protocol that combines features of both distance vector and link-state protocols.

### Question 5
What is the primary purpose of VLANs (Virtual Local Area Networks)?
A) To increase network speed
B) To logically segment a physical network into multiple broadcast domains
C) To reduce network costs
D) To improve physical security

**Answer: B) To logically segment a physical network into multiple broadcast domains**

**Explanation:** VLANs allow network administrators to create separate broadcast domains within a single physical network infrastructure. This improves security, reduces broadcast traffic, and allows for better network management and organization.

## Chapter 2: Network Security & Infrastructure Protection

### Question 6
What is the main difference between stateful and stateless firewalls?
A) Stateful firewalls are faster than stateless firewalls
B) Stateful firewalls track connection state while stateless firewalls examine individual packets
C) Stateless firewalls provide better security than stateful firewalls
D) There is no significant difference between them

**Answer: B) Stateful firewalls track connection state while stateless firewalls examine individual packets**

**Explanation:** Stateful firewalls maintain a state table to track active connections and make decisions based on the context of the connection. Stateless firewalls examine each packet individually without considering the connection state, making them faster but less secure.

### Question 7
Which of the following is NOT a type of Intrusion Prevention System (IPS)?
A) Network-based IPS
B) Host-based IPS
C) Signature-based IPS
D) Application-based IPS

**Answer: D) Application-based IPS**

**Explanation:** The main types of IPS are Network-based IPS (NIPS), Host-based IPS (HIPS), and Signature-based IPS. Application-based IPS is not a recognized category of IPS.

### Question 8
What does the "S" in IPSec stand for?
A) Security
B) Secure
C) System
D) Service

**Answer: A) Security**

**Explanation:** IPSec stands for Internet Protocol Security. It's a suite of protocols used to secure IP communications by authenticating and encrypting IP packets.

### Question 9
Which VPN protocol is considered the most secure?
A) PPTP
B) L2TP
C) SSTP
D) IKEv2

**Answer: D) IKEv2**

**Explanation:** IKEv2 (Internet Key Exchange version 2) is considered one of the most secure VPN protocols. It provides strong encryption, excellent stability, and is resistant to attacks. While SSTP is also secure, IKEv2 is generally considered superior in terms of security and performance.

### Question 10
What is the primary purpose of a Demilitarized Zone (DMZ)?
A) To store backup data
B) To isolate public-facing services from the internal network
C) To increase network speed
D) To reduce network costs

**Answer: B) To isolate public-facing services from the internal network**

**Explanation:** A DMZ (Demilitarized Zone) is a network segment that sits between the internal network and the external network (like the internet). It contains public-facing services like web servers, email servers, etc., isolating them from the internal network to limit exposure to attacks.

## Chapter 3: Server Administration - Windows & Linux

### Question 11
Which Active Directory component is responsible for holding a read-only copy of the schema and configuration partitions?
A) Global Catalog Server
B) Domain Controller
C) Read-Only Domain Controller
D) Schema Master

**Answer: A) Global Catalog Server**

**Explanation:** A Global Catalog Server holds a partial, read-only copy of all domain objects in the forest, including the schema and configuration partitions. This allows for faster authentication and searching across domains.

### Question 12
What is the default port for SSH?
A) 21
B) 22
C) 23
D) 25

**Answer: B) 22**

**Explanation:** SSH (Secure Shell) uses port 22 by default. This is a standard port number assigned to SSH for secure remote access to systems.

### Question 13
Which Linux command is used to change file permissions?
A) chown
B) chmod
C) chattr
D) chgrp

**Answer: B) chmod**

**Explanation:** The chmod command is used to change file and directory permissions in Linux. The command stands for "change mode" and allows setting read, write, and execute permissions for owner, group, and others.

### Question 14
What is the primary function of systemd in Linux?
A) File system management
B) Package management
C) System and service manager
D) Network configuration

**Answer: C) System and service manager**

**Explanation:** systemd is a system and service manager for Linux operating systems. It serves as the init system, starting and managing system processes, services, and daemons.

### Question 15
Which Windows Server role provides certificate services for PKI?
A) Active Directory Federation Services
B) Active Directory Certificate Services
C) Active Directory Rights Management Services
D) Active Directory Lightweight Directory Services

**Answer: B) Active Directory Certificate Services**

**Explanation:** Active Directory Certificate Services (AD CS) is the Windows Server role that provides certificate services for Public Key Infrastructure (PKI). It enables the creation, management, and distribution of digital certificates.

## Chapter 4: Database Management Systems

### Question 16
Which of the following is NOT one of the ACID properties of database transactions?
A) Atomicity
B) Consistency
C) Isolation
D) Integration

**Answer: D) Integration**

**Explanation:** The ACID properties are Atomicity, Consistency, Isolation, and Durability. Integration is not one of these properties.

### Question 17
In SQL, which JOIN returns all rows from the left table and matched rows from the right table?
A) INNER JOIN
B) RIGHT JOIN
C) LEFT JOIN
D) FULL OUTER JOIN

**Answer: C) LEFT JOIN**

**Explanation:** A LEFT JOIN returns all rows from the left table and the matched rows from the right table. If there's no match, NULL values are returned for right table columns.

### Question 18
What is the purpose of database normalization?
A) To increase database speed
B) To reduce redundancy and improve data integrity
C) To reduce database size
D) To improve backup performance

**Answer: B) To reduce redundancy and improve data integrity**

**Explanation:** Database normalization is the process of organizing data in a database to reduce redundancy and improve data integrity. It involves decomposing tables to eliminate data duplication and ensure referential integrity.

### Question 19
Which SQL clause is used to filter groups created by GROUP BY?
A) WHERE
B) HAVING
C) ORDER BY
D) DISTINCT

**Answer: B) HAVING**

**Explanation:** The HAVING clause is used to filter groups created by the GROUP BY clause. Unlike WHERE which filters individual rows, HAVING filters aggregated results after grouping.

### Question 20
What is the difference between a clustered and non-clustered index?
A) Clustered indexes are faster than non-clustered indexes
B) Clustered indexes determine physical storage order, non-clustered do not
C) Non-clustered indexes can only be created on primary keys
D) There is no significant difference

**Answer: B) Clustered indexes determine physical storage order, non-clustered do not**

**Explanation:** A clustered index determines the physical order of data in a table, meaning there can only be one clustered index per table. A non-clustered index is a separate structure that contains index key values and row locators, allowing multiple non-clustered indexes per table.

## Chapter 5: Data Structures & Algorithms

### Question 21
What is the time complexity of searching in a balanced binary search tree?
A) O(1)
B) O(log n)
C) O(n)
D) O(n log n)

**Answer: B) O(log n)**

**Explanation:** In a balanced binary search tree, the height of the tree is log n, so searching takes O(log n) time as we eliminate half of the remaining nodes at each step.

### Question 22
Which data structure follows the Last In, First Out (LIFO) principle?
A) Queue
B) Stack
C) Array
D) Linked List

**Answer: B) Stack**

**Explanation:** A stack follows the Last In, First Out (LIFO) principle, where the last element added is the first one to be removed. Common operations are push (add) and pop (remove).

### Question 23
What is the time complexity of bubble sort in the worst case?
A) O(1)
B) O(log n)
C) O(n)
D) O(n²)

**Answer: D) O(n²)**

**Explanation:** Bubble sort has a worst-case time complexity of O(n²) because in the worst case, it needs to make n comparisons for each of the n elements, resulting in n×n operations.

### Question 24
Which traversal visits the root node first, then the left subtree, then the right subtree?
A) Inorder
B) Preorder
C) Postorder
D) Level-order

**Answer: B) Preorder**

**Explanation:** Preorder traversal visits nodes in the order: Root, Left subtree, Right subtree. This is commonly used for creating a copy of the tree.

### Question 25
What is the primary advantage of a hash table over a binary search tree?
A) Lower space complexity
B) Faster average case operations
C) Maintains sorted order
D) Simpler implementation

**Answer: B) Faster average case operations**

**Explanation:** Hash tables provide O(1) average case time complexity for search, insert, and delete operations, while balanced binary search trees provide O(log n) operations. However, BSTs maintain sorted order which hash tables do not.

## Chapter 6: Object-Oriented Programming (OOP)

### Question 26
Which OOP principle allows a subclass to provide a specific implementation of a method already defined in its parent class?
A) Encapsulation
B) Inheritance
C) Polymorphism
D) Abstraction

**Answer: C) Polymorphism**

**Explanation:** Polymorphism, specifically method overriding, allows a subclass to provide a specific implementation of a method already defined in its parent class. This is achieved through runtime polymorphism.

### Question 27
What is the main purpose of encapsulation in OOP?
A) To enable code reuse
B) To hide internal implementation details
C) To create multiple instances of a class
D) To define abstract methods

**Answer: B) To hide internal implementation details**

**Explanation:** Encapsulation is the bundling of data and methods that operate on that data within a single unit (class) and restricting access to internal components. It hides internal implementation details and exposes only necessary functionality.

### Question 28
Which design pattern ensures that a class has only one instance and provides a global point of access to it?
A) Factory Pattern
B) Observer Pattern
C) Singleton Pattern
D) Strategy Pattern

**Answer: C) Singleton Pattern**

**Explanation:** The Singleton pattern ensures that a class has only one instance throughout the application lifecycle and provides a global point of access to that instance.

### Question 29
What is the difference between method overloading and method overriding?
A) Overloading occurs in the same class, overriding occurs between parent and child classes
B) Overriding occurs in the same class, overloading occurs between parent and child classes
C) There is no difference between them
D) Overloading is faster than overriding

**Answer: A) Overloading occurs in the same class, overriding occurs between parent and child classes**

**Explanation:** Method overloading occurs when multiple methods with the same name but different parameters exist in the same class. Method overriding occurs when a subclass provides a specific implementation of a method already defined in its parent class.

### Question 30
Which SOLID principle states that "software entities should be open for extension but closed for modification"?
A) Single Responsibility Principle
B) Open/Closed Principle
C) Liskov Substitution Principle
D) Interface Segregation Principle

**Answer: B) Open/Closed Principle**

**Explanation:** The Open/Closed Principle states that software entities (classes, modules, functions, etc.) should be open for extension but closed for modification. This means you should be able to extend the behavior of a module without modifying its source code.

## Chapter 7: Software Development Methodologies

### Question 31
Which SDLC model follows a sequential approach with distinct phases?
A) Agile
B) Waterfall
C) Spiral
D) Iterative

**Answer: B) Waterfall**

**Explanation:** The Waterfall model follows a sequential approach where each phase must be completed before the next one begins. The phases are typically Requirements, Design, Implementation, Verification, and Maintenance.

### Question 32
In Scrum, what is the typical duration of a Sprint?
A) 1-2 weeks
B) 2-4 weeks
C) 1 month
D) 3 months

**Answer: B) 2-4 weeks**

**Explanation:** In Scrum, a Sprint typically lasts 2-4 weeks. The duration is fixed for the duration of the project and creates a consistent rhythm for the development team.

### Question 33
Which Agile framework emphasizes visual workflow management?
A) Scrum
B) Kanban
C) XP
D) Lean

**Answer: B) Kanban**

**Explanation:** Kanban is an Agile framework that emphasizes visual workflow management using Kanban boards. It focuses on continuous flow and limiting work in progress (WIP).

### Question 34
What is the primary purpose of Test-Driven Development (TDD)?
A) To reduce documentation
B) To write tests before implementation code
C) To eliminate the need for debugging
D) To speed up the development process

**Answer: B) To write tests before implementation code**

**Explanation:** Test-Driven Development (TDD) is a software development approach where tests are written before the implementation code. The cycle is Red (write failing test), Green (make test pass), Refactor (improve code structure).

### Question 35
Which DevOps practice automates the process of building, testing, and deploying code?
A) Infrastructure as Code
B) Continuous Integration/Continuous Deployment (CI/CD)
C) Configuration Management
D) Containerization

**Answer: B) Continuous Integration/Continuous Deployment (CI/CD)**

**Explanation:** CI/CD is a DevOps practice that automates the process of integrating code changes, testing them, and deploying them to production. It ensures faster and more reliable software delivery.

## Chapter 8: Cloud Computing & Virtualization

### Question 36
Which cloud service model provides virtualized computing resources over the internet?
A) SaaS
B) PaaS
C) IaaS
D) FaaS

**Answer: C) IaaS**

**Explanation:** IaaS (Infrastructure as a Service) provides virtualized computing resources such as virtual machines, storage, and networks over the internet. Examples include Amazon EC2 and Microsoft Azure Virtual Machines.

### Question 37
What is the main difference between Type 1 and Type 2 hypervisors?
A) Type 1 runs on top of an operating system, Type 2 runs directly on hardware
B) Type 1 runs directly on hardware, Type 2 runs on top of an operating system
C) Type 1 is open source, Type 2 is proprietary
D) There is no significant difference

**Answer: B) Type 1 runs directly on hardware, Type 2 runs on top of an operating system**

**Explanation:** Type 1 hypervisors (bare-metal) run directly on the host hardware, while Type 2 hypervisors (hosted) run on top of a conventional operating system like Windows or Linux.

### Question 38
Which AWS service is used for object storage?
A) Amazon EC2
B) Amazon S3
C) Amazon RDS
D) Amazon VPC

**Answer: B) Amazon S3**

**Explanation:** Amazon S3 (Simple Storage Service) is Amazon's object storage service designed to store and retrieve any amount of data from anywhere on the web.

### Question 39
What does the term "serverless computing" mean?
A) Servers are not used at all
B) The cloud provider manages server infrastructure
C) Applications run without any backend
D) Physical servers are replaced with virtual servers

**Answer: B) The cloud provider manages server infrastructure**

**Explanation:** Serverless computing means that the cloud provider manages the server infrastructure, automatically scaling applications and charging based on actual usage rather than pre-purchased capacity. Servers still exist, but the management is abstracted away.

### Question 40
Which cloud deployment model provides infrastructure for exclusive use by a single organization?
A) Public Cloud
B) Private Cloud
C) Hybrid Cloud
D) Community Cloud

**Answer: B) Private Cloud**

**Explanation:** A Private Cloud provides cloud infrastructure for exclusive use by a single organization. It may be managed internally or by a third party and may exist on or off premises.

## Chapter 9: Cybersecurity & Information Security

### Question 41
What are the three components of the CIA triad?
A) Confidentiality, Integrity, Availability
B) Control, Identification, Authentication
C) Communication, Integration, Authorization
D) Certification, Implementation, Assessment

**Answer: A) Confidentiality, Integrity, Availability**

**Explanation:** The CIA triad consists of Confidentiality (ensuring information is accessible only to authorized individuals), Integrity (ensuring information remains accurate and complete), and Availability (ensuring information and systems are accessible when needed).

### Question 42
Which authentication factor involves something you have?
A) Knowledge factor
B) Possession factor
C) Inherence factor
D) Location factor

**Answer: B) Possession factor**

**Explanation:** The possession factor involves something you have, such as a smart card, token, or mobile device. The three main authentication factors are: something you know (knowledge), something you have (possession), and something you are (inherence/biometrics).

### Question 43
What is the primary purpose of a Public Key Infrastructure (PKI)?
A) To encrypt all network traffic
B) To manage digital certificates and public-key encryption
C) To authenticate users to systems
D) To prevent malware infections

**Answer: B) To manage digital certificates and public-key encryption**

**Explanation:** PKI (Public Key Infrastructure) is a framework that manages digital certificates and public-key encryption. It provides a secure method for binding public keys with identities and enables secure communication.

### Question 44
Which type of malware is designed to encrypt victim's data and demand payment?
A) Virus
B) Worm
C) Trojan
D) Ransomware

**Answer: D) Ransomware**

**Explanation:** Ransomware is a type of malware that encrypts the victim's data and demands payment (ransom) to decrypt the data. It has become one of the most significant cybersecurity threats.

### Question 45
What does the acronym GDPR stand for?
A) Global Data Protection Regulation
B) General Data Protection Regulation
C) Government Data Privacy Rules
D) General Digital Privacy Regulation

**Answer: B) General Data Protection Regulation**

**Explanation:** GDPR stands for General Data Protection Regulation, which is a regulation in EU law on data protection and privacy in the European Union and the European Economic Area.

## Chapter 10: Storage Technologies & Data Management

### Question 46
Which RAID level provides striping with parity and can survive a single drive failure?
A) RAID 0
B) RAID 1
C) RAID 5
D) RAID 10

**Answer: C) RAID 5**

**Explanation:** RAID 5 uses striping with distributed parity across all drives. It can survive a single drive failure since the parity information can be used to reconstruct the missing data from the failed drive.

### Question 47
What is the main difference between NAS and SAN storage?
A) NAS is faster than SAN
B) NAS provides file-level access, SAN provides block-level access
C) SAN is cheaper than NAS
D) There is no significant difference

**Answer: B) NAS provides file-level access, SAN provides block-level access**

**Explanation:** NAS (Network Attached Storage) provides file-level access using protocols like NFS or SMB/CIFS, while SAN (Storage Area Network) provides block-level access using protocols like Fibre Channel or iSCSI.

### Question 48
What does the 3-2-1 backup rule recommend?
A) 3 copies of data, 2 different people, 1 location
B) 3 copies of data, 2 different media types, 1 offsite copy
C) 3 different backup methods, 2 locations, 1 person responsible
D) 3 copies of data, 2 different software, 1 hardware

**Answer: B) 3 copies of data, 2 different media types, 1 offsite copy**

**Explanation:** The 3-2-1 backup rule recommends having 3 copies of your data (1 primary + 2 backups), on 2 different media types (e.g., disk and tape), with 1 copy stored offsite.

### Question 49
Which storage protocol is commonly used for Storage Area Networks (SANs)?
A) NFS
B) SMB/CIFS
C) Fibre Channel
D) FTP

**Answer: C) Fibre Channel**

**Explanation:** Fibre Channel is a high-speed network technology primarily used for SANs. It provides high-performance, reliable connections between servers and shared storage devices.

### Question 50
What is the difference between RTO and RPO?
A) RTO is about data, RPO is about time
B) RTO is recovery time objective, RPO is recovery point objective
C) RPO is about data, RTO is about time
D) There is no difference between them

**Answer: B) RTO is recovery time objective, RPO is recovery point objective**

**Explanation:** RTO (Recovery Time Objective) is the maximum acceptable downtime for a system or application, while RPO (Recovery Point Objective) is the maximum acceptable data loss measured in time (how much data can be lost).

## Chapter 11: IT Governance & Policy Development

### Question 51
What does ITIL stand for?
A) Information Technology Infrastructure Library
B) Information Technology Implementation Lifecycle
C) Information Technology Integration Layer
D) Information Technology Innovation Lab

**Answer: A) Information Technology Infrastructure Library**

**Explanation:** ITIL stands for Information Technology Infrastructure Library, which is a framework of best practices for IT service management that focuses on aligning IT services with business needs.

### Question 52
Which ITIL practice focuses on minimizing the negative impact of incidents?
A) Problem Management
B) Incident Management
C) Change Management
D) Service Level Management

**Answer: B) Incident Management**

**Explanation:** Incident Management is the ITIL practice that focuses on minimizing the negative impact of incidents by restoring normal service operation as quickly as possible.

### Question 53
What is the purpose of a Service Level Agreement (SLA)?
A) To define the technical architecture of services
B) To contractually define service expectations and quality levels
C) To document internal processes
D) To list all system components

**Answer: B) To contractually define service expectations and quality levels**

**Explanation:** An SLA (Service Level Agreement) is a contract between a service provider and a customer that defines the expected service quality, availability, responsibilities, and metrics.

### Question 54
Which COBIT domain focuses on governance and direction of the enterprise?
A) Build, Acquire, and Implement (BAI)
B) Deliver, Service, and Support (DSS)
C) Evaluate, Direct, and Monitor (EDM)
D) Align, Plan, and Organize (APO)

**Answer: C) Evaluate, Direct, and Monitor (EDM)**

**Explanation:** In COBIT 2019, EDM (Evaluate, Direct, and Monitor) is the governance domain that focuses on providing governance and direction for the enterprise.

### Question 55
What does the acronym COBIT stand for?
A) Control Objectives for Information and Related Technology
B) Computer Operations and Business Integration Toolkit
C) Corporate Oversight and Business Implementation Tool
D) Certified Operations and Business Information Technology

**Answer: A) Control Objectives for Information and Related Technology**

**Explanation:** COBIT stands for Control Objectives for Information and Related Technology. It's a framework for IT management and governance developed by ISACA.

## Chapter 12: Big Data & Modern Technologies

### Question 56
What are the five V's of big data?
A) Volume, Velocity, Variety, Veracity, Value
B) Volume, Velocity, Visibility, Validity, Value
C) Volume, Velocity, Variety, Verification, Vision
D) Volume, Velocity, Vulnerability, Veracity, Value

**Answer: A) Volume, Velocity, Variety, Veracity, Value**

**Explanation:** The five V's of big data are: Volume (amount of data), Velocity (speed of data generation), Variety (types of data), Veracity (quality of data), and Value (extraction of insights from data).

### Question 57
Which Hadoop component is responsible for resource management and job scheduling?
A) HDFS
B) MapReduce
C) YARN
D) Hive

**Answer: C) YARN**

**Explanation:** YARN (Yet Another Resource Negotiator) is the Hadoop component responsible for resource management and job scheduling in Hadoop 2.x and later versions.

### Question 58
What is the main difference between batch processing and stream processing?
A) Batch is faster than stream processing
B) Batch processes data in real-time, stream processes data in batches
C) Stream processes data in real-time, batch processes data in batches
D) There is no significant difference

**Answer: C) Stream processes data in real-time, batch processes data in batches**

**Explanation:** Stream processing handles data as it arrives in real-time, while batch processing handles large volumes of data in scheduled batches. Stream processing has lower latency but batch processing can handle larger volumes.

### Question 59
Which NoSQL database type is best suited for social network data with complex relationships?
A) Key-value store
B) Document store
C) Column-family store
D) Graph database

**Answer: D) Graph database**

**Explanation:** Graph databases are specifically designed to handle data with complex relationships, making them ideal for social networks, recommendation engines, and other applications where relationships between entities are important.

### Question 60
What is the primary purpose of MapReduce?
A) To store big data
B) To process big data in parallel across clusters
C) To visualize big data
D) To secure big data

**Answer: B) To process big data in parallel across clusters**

**Explanation:** MapReduce is a programming model and framework for processing and generating large data sets with a parallel, distributed algorithm on a cluster. It consists of a Map procedure that performs filtering and sorting, and a Reduce procedure that performs a summary operation.

## Chapter 13: Network Protocols & Communication

### Question 61
What is the three-way handshake in TCP?
A) SYN, ACK, FIN
B) SYN, SYN-ACK, ACK
C) REQUEST, RESPONSE, CONFIRM
D) CONNECT, ESTABLISH, READY

**Answer: B) SYN, SYN-ACK, ACK**

**Explanation:** The TCP three-way handshake establishes a connection with these steps: 1) Client sends SYN to server, 2) Server responds with SYN-ACK, 3) Client sends ACK to server. This ensures both sides are ready to communicate.

### Question 62
Which protocol is used for secure web browsing?
A) HTTP
B) HTTPS
C) FTP
D) SMTP

**Answer: B) HTTPS**

**Explanation:** HTTPS (HTTP Secure) is the secure version of HTTP that uses SSL/TLS encryption to secure communications between a web browser and a web server.

### Question 63
What is the default port for DNS?
A) 25
B) 53
C) 80
D) 443

**Answer: B) 53**

**Explanation:** DNS (Domain Name System) uses port 53 by default for both TCP and UDP communications.

### Question 64
Which protocol is used for email retrieval from a server?
A) SMTP
B) SNMP
C) POP3
D) DHCP

**Answer: C) POP3**

**Explanation:** POP3 (Post Office Protocol version 3) is used for retrieving email from a mail server. SMTP is used for sending email, while IMAP is another protocol for email retrieval.

### Question 65
What does the acronym QoS stand for in networking?
A) Quality of Service
B) Quick Operating System
C) Query Optimization System
D) Quantum Operating System

**Answer: A) Quality of Service**

**Explanation:** QoS (Quality of Service) refers to network capabilities that provide guaranteed traffic priority and performance for specific applications or data flows.

## Chapter 14: Computer Hardware & Architecture

### Question 66
What is the main difference between von Neumann and Harvard architectures?
A) Harvard is faster than von Neumann
B) von Neumann uses separate memory for instructions and data
C) Harvard uses separate memory for instructions and data
D) There is no significant difference

**Answer: C) Harvard uses separate memory for instructions and data**

**Explanation:** In Harvard architecture, there are separate memory systems for instructions and data, while in von Neumann architecture, both instructions and data share the same memory system.

### Question 67
Which cache level is typically the fastest but smallest?
A) L1 cache
B) L2 cache
C) L3 cache
D) L4 cache

**Answer: A) L1 cache**

**Explanation:** L1 cache is the fastest and smallest cache level, located closest to the CPU core. L2 and L3 caches are progressively larger but slower.

### Question 68
What does the acronym ECC stand for in relation to RAM?
A) Extended Capacity Computing
B) Error Correction Code
C) Enhanced Circuit Computing
D) Electronic Component Control

**Answer: B) Error Correction Code**

**Explanation:** ECC (Error Correction Code) RAM can detect and correct single-bit errors automatically, making it more reliable for servers and critical applications.

### Question 69
Which storage technology uses floating-gate transistors and is commonly used in SSDs?
A) DRAM
B) SRAM
C) Flash memory
D) Magnetic storage

**Answer: C) Flash memory**

**Explanation:** Flash memory uses floating-gate transistors and is the technology commonly used in SSDs, USB drives, and memory cards. It's a type of non-volatile memory.

### Question 70
What does the acronym POST stand for in computer hardware?
A) Power On System Test
B) Power On Self Test
C) Primary Operating System Test
D) Peripheral Output System Test

**Answer: B) Power On Self Test**

**Explanation:** POST (Power-On Self-Test) is a built-in diagnostic testing sequence that runs when a computer is powered on to check hardware components before loading the operating system.

## Chapter 15: Project Management & Financial Aspects

### Question 71
What are the five process groups in PMBOK?
A) Initiation, Planning, Execution, Monitoring & Controlling, Closing
B) Planning, Design, Development, Testing, Deployment
C) Requirements, Analysis, Design, Implementation, Maintenance
D) Concept, Development, Implementation, Operations, Disposal

**Answer: A) Initiation, Planning, Execution, Monitoring & Controlling, Closing**

**Explanation:** The five process groups in PMBOK (Project Management Body of Knowledge) are: Initiating, Planning, Executing, Monitoring and Controlling, and Closing.

### Question 72
What does the acronym WBS stand for in project management?
A) Work Breakdown Schedule
B) Work Budget System
C) Work Breakdown Structure
D) Work Benchmark System

**Answer: C) Work Breakdown Structure**

**Explanation:** WBS (Work Breakdown Structure) is a hierarchical decomposition of the total scope of work to accomplish project objectives and create required deliverables.

### Question 73
What is the Critical Path in project management?
A) The shortest path through the project network
B) The longest path through the project network
C) The path with the most resources
D) The path with the lowest cost

**Answer: B) The longest path through the project network**

**Explanation:** The Critical Path is the longest sequence of activities in a project plan that must be completed on time for the project to meet its deadline. Any delay in critical path activities will delay the project.

### Question 74
What does the Cost Performance Index (CPI) measure?
A) Schedule efficiency
B) Cost efficiency
C) Quality performance
D) Resource utilization

**Answer: B) Cost efficiency**

**Explanation:** The Cost Performance Index (CPI) measures cost efficiency of work performed. It is calculated as CPI = EV / AC (Earned Value divided by Actual Cost). A CPI > 1 indicates cost efficiency.

### Question 75
Which risk response strategy involves transferring the risk to another party?
A) Avoid
B) Mitigate
C) Accept
D) Transfer

**Answer: D) Transfer**

**Explanation:** Risk transfer involves shifting the impact of a risk and the responsibility for its management to a third party, typically through insurance, contracts, or guarantees.

## Mixed Questions Covering Multiple Chapters

### Question 76
Which cloud service model provides a platform allowing customers to develop, run, and manage applications without dealing with the underlying infrastructure?
A) IaaS
B) PaaS
C) SaaS
D) FaaS

**Answer: B) PaaS**

**Explanation:** PaaS (Platform as a Service) provides a platform allowing customers to develop, run, and manage applications without dealing with the underlying infrastructure. Examples include Google App Engine and Microsoft Azure App Service.

### Question 77
In the OSI model, which layer is responsible for routing and logical addressing?
A) Physical Layer
B) Data Link Layer
C) Network Layer
D) Transport Layer

**Answer: C) Network Layer**

**Explanation:** The Network Layer (Layer 3) is responsible for routing and logical addressing. It handles the routing of data between different networks and uses logical addresses (IP addresses) to determine the best path for data transmission.

### Question 78
Which RAID level provides mirroring for redundancy?
A) RAID 0
B) RAID 1
C) RAID 5
D) RAID 6

**Answer: B) RAID 1**

**Explanation:** RAID 1 provides mirroring, where data is written identically to two drives, providing complete redundancy. If one drive fails, the other contains a complete copy of the data.

### Question 79
What is the primary purpose of a firewall in network security?
A) To increase network speed
B) To control incoming and outgoing network traffic
C) To store network data
D) To route network traffic

**Answer: B) To control incoming and outgoing network traffic**

**Explanation:** A firewall is a network security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules. It acts as a barrier between trusted and untrusted networks.

### Question 80
Which TCP port is commonly used for secure web traffic (HTTPS)?
A) 22
B) 25
C) 80
D) 443

**Answer: D) 443**

**Explanation:** Port 443 is the standard port for HTTPS (HTTP Secure) traffic, which uses SSL/TLS encryption to secure communications between web browsers and servers.

### Question 81
In database terminology, what does ACID stand for?
A) Atomicity, Consistency, Isolation, Durability
B) Accuracy, Completeness, Integrity, Dependability
C) Access, Control, Integrity, Distribution
D) Authentication, Confidentiality, Integrity, Detection

**Answer: A) Atomicity, Consistency, Isolation, Durability**

**Explanation:** ACID is an acronym that stands for Atomicity, Consistency, Isolation, and Durability. These are properties that guarantee that database transactions are processed reliably.

### Question 82
Which RAID configuration can survive two simultaneous drive failures?
A) RAID 0
B) RAID 1
C) RAID 5
D) RAID 6

**Answer: D) RAID 6**

**Explanation:** RAID 6 uses dual parity, which allows it to survive up to two simultaneous drive failures. RAID 5 can only survive one drive failure.

### Question 83
What is the primary function of DNS?
A) To encrypt network traffic
B) To translate domain names to IP addresses
C) To route network packets
D) To authenticate users

**Answer: B) To translate domain names to IP addresses**

**Explanation:** DNS (Domain Name System) translates human-readable domain names (like www.example.com) into IP addresses that computers use to identify each other on the network.

### Question 84
Which cloud deployment model combines public and private clouds?
A) Public Cloud
B) Private Cloud
C) Hybrid Cloud
D) Community Cloud

**Answer: C) Hybrid Cloud**

**Explanation:** A Hybrid Cloud combines public and private cloud environments, allowing data and applications to be shared between them. This provides greater flexibility and optimization of existing infrastructure.

### Question 85
What does the term "virtualization" refer to in computing?
A) Creating virtual versions of physical resources
B) Making computers faster
C) Connecting computers over a network
D) Storing data in the cloud

**Answer: A) Creating virtual versions of physical resources**

**Explanation:** Virtualization refers to the creation of virtual versions of physical resources such as servers, storage devices, or network resources. It allows multiple virtual machines to run on a single physical machine.

### Question 86
Which HTTP status code indicates "Not Found"?
A) 200
B) 301
C) 404
D) 500

**Answer: C) 404**

**Explanation:** HTTP status code 404 indicates "Not Found," meaning the requested resource could not be found on the server.

### Question 87
What is the primary purpose of encryption in cybersecurity?
A) To compress data
B) To make data unreadable to unauthorized parties
C) To speed up data transmission
D) To reduce storage requirements

**Answer: B) To make data unreadable to unauthorized parties**

**Explanation:** Encryption is the process of converting data into a coded format that can only be read by someone who has the key to decrypt it, protecting data from unauthorized access.

### Question 88
Which TCP flag is used to initiate a connection?
A) ACK
B) FIN
C) RST
D) SYN

**Answer: D) SYN**

**Explanation:** The SYN (Synchronize) flag is used in the TCP three-way handshake to initiate a connection. The client sends a SYN packet to the server to begin establishing a connection.

### Question 89
What is the main advantage of SSDs over HDDs?
A) Lower cost per GB
B) Higher storage capacity
C) Faster access times
D) Better for archival storage

**Answer: C) Faster access times**

**Explanation:** SSDs (Solid State Drives) have significantly faster access times than HDDs (Hard Disk Drives) because they have no moving parts. This results in faster boot times, file access, and overall system performance.

### Question 90
Which protocol is used for email delivery between mail servers?
A) POP3
B) IMAP
C) SMTP
D) FTP

**Answer: C) SMTP**

**Explanation:** SMTP (Simple Mail Transfer Protocol) is used for sending and delivering email between mail servers. POP3 and IMAP are used for retrieving email from servers.

### Question 91
What does the acronym VPN stand for?
A) Virtual Private Network
B) Verified Public Network
C) Virtual Process Network
D) Verified Process Node

**Answer: A) Virtual Private Network**

**Explanation:** VPN (Virtual Private Network) creates a secure, encrypted connection over a less secure network, such as the internet, allowing remote access to private networks.

### Question 92
Which RAID level provides both striping and mirroring?
A) RAID 0
B) RAID 1
C) RAID 5
D) RAID 10

**Answer: D) RAID 10**

**Explanation:** RAID 10 (also known as RAID 1+0) combines mirroring and striping. It creates mirrored pairs of drives and then stripes data across these mirrored pairs, providing both performance and redundancy.

### Question 93
What is the primary purpose of a DMZ (Demilitarized Zone) in network security?
A) To store backup data
B) To isolate public-facing services from the internal network
C) To increase network speed
D) To reduce network costs

**Answer: B) To isolate public-facing services from the internal network**

**Explanation:** A DMZ is a network segment that sits between the internal network and the external network (like the internet). It contains public-facing services like web servers, isolating them from the internal network to limit exposure to attacks.

### Question 94
Which HTTP method is used to retrieve data from a server?
A) POST
B) GET
C) PUT
D) DELETE

**Answer: B) GET**

**Explanation:** The GET method is used to retrieve data from a server. It requests data from a specified resource and should only be used to retrieve data, not to modify it.

### Question 95
What is the main difference between TCP and UDP?
A) TCP is faster than UDP
B) TCP is connection-oriented, UDP is connectionless
C) UDP provides more security than TCP
D) There is no significant difference

**Answer: B) TCP is connection-oriented, UDP is connectionless**

**Explanation:** TCP (Transmission Control Protocol) is connection-oriented and provides reliable, ordered delivery of data. UDP (User Datagram Protocol) is connectionless and provides faster but less reliable data transmission.

### Question 96
Which cloud service model provides software applications over the internet?
A) IaaS
B) PaaS
C) SaaS
D) CaaS

**Answer: C) SaaS**

**Explanation:** SaaS (Software as a Service) provides software applications over the internet on a subscription basis. Examples include Gmail, Salesforce, and Microsoft Office 365.

### Question 97
What is the primary function of a router in networking?
A) To connect devices within a local network
B) To connect different networks and route traffic between them
C) To amplify network signals
D) To store network data

**Answer: B) To connect different networks and route traffic between them**

**Explanation:** A router connects different networks and determines the best path for data packets to travel from source to destination. It operates at the network layer (Layer 3) of the OSI model.

### Question 98
Which authentication method uses biometric data?
A) Password-based authentication
B) Multi-factor authentication
C) Biometric authentication
D) Certificate-based authentication

**Answer: C) Biometric authentication**

**Explanation:** Biometric authentication uses unique biological characteristics such as fingerprints, facial recognition, or iris scans to verify identity.

### Question 99
What does the acronym DHCP stand for?
A) Dynamic Host Configuration Protocol
B) Direct Host Communication Protocol
C) Distributed Hardware Control Protocol
D) Digital Host Configuration Process

**Answer: A) Dynamic Host Configuration Protocol**

**Explanation:** DHCP (Dynamic Host Configuration Protocol) automatically assigns IP addresses and other network configuration parameters to devices on a network.

### Question 100
Which RAID level provides the highest performance but no redundancy?
A) RAID 0
B) RAID 1
C) RAID 5
D) RAID 6

**Answer: A) RAID 0**

**Explanation:** RAID 0 provides the highest performance through striping, but offers no redundancy. If any drive in the array fails, all data is lost.