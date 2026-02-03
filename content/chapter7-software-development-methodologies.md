# Chapter 7: Software Development Methodologies

## Introduction

Software development methodologies provide structured approaches to building software applications. As an Assistant Director IT, understanding these methodologies is crucial for managing software projects, selecting appropriate approaches for different scenarios, and making informed decisions about technology investments. This chapter covers various SDLC models, agile frameworks, testing methodologies, DevOps practices, and other important development concepts.

## SDLC Models

### Waterfall: Sequential Phases, Documentation-Heavy

#### Overview
- **Concept**: Sequential development model with distinct phases
- **Phases**: Requirements → Design → Implementation → Verification → Maintenance
- **Approach**: Linear progression from one phase to the next
- **Characteristics**: Heavy documentation, rigid structure

#### Advantages
- **Clear structure**: Well-defined phases and deliverables
- **Easy to manage**: Progress measured against plan
- **Documentation**: Comprehensive documentation for future reference
- **Suitable for**: Projects with well-defined requirements

#### Disadvantages
- **Inflexibility**: Difficult to accommodate changes
- **Late testing**: Testing occurs late in the cycle
- **Customer feedback**: Limited customer involvement until end
- **Risk**: High risk of project failure if requirements change

#### When to Use
- Requirements are well understood and stable
- Project scope is clearly defined
- Technology is proven and familiar
- Customer requirements are unlikely to change

### Agile: Iterative, Incremental, Customer Collaboration

#### Overview
- **Concept**: Iterative development with frequent releases
- **Principles**: Individuals and interactions, working software, customer collaboration, responding to change
- **Approach**: Deliver working software in short iterations
- **Values**: Emphasizes flexibility and customer satisfaction

#### Advantages
- **Flexibility**: Adapt to changing requirements
- **Customer involvement**: Continuous feedback and collaboration
- **Early delivery**: Working software delivered early and often
- **Team collaboration**: Promotes teamwork and communication

#### Disadvantages
- **Documentation**: Less emphasis on documentation
- **Planning**: Difficult to estimate effort and timeline
- **Scope creep**: Risk of expanding scope without control
- **Requires skilled teams**: Needs experienced and disciplined developers

#### Core Principles
- **Customer satisfaction**: Through early and continuous delivery
- **Welcome changes**: Even late in development
- **Working software**: Primary measure of progress
- **Sustainable development**: Maintain constant pace
- **Technical excellence**: Continuous attention to good design

### Spiral: Risk-Driven, Prototyping

#### Overview
- **Concept**: Combines iterative development with systematic risk analysis
- **Phases**: Planning, risk analysis, engineering, evaluation
- **Approach**: Spiral motion through phases with increasing detail
- **Emphasis**: Risk identification and mitigation

#### Advantages
- **Risk management**: Systematic approach to risk identification
- **Flexibility**: Accommodates changes based on risk analysis
- **Prototyping**: Early validation of critical features
- **Customer feedback**: Regular evaluation and feedback

#### Disadvantages
- **Complexity**: More complex than other models
- **Cost**: Potentially expensive due to risk analysis
- **Expertise**: Requires risk assessment expertise
- **Documentation**: Extensive documentation requirements

#### Spiral Phases
1. **Identify objectives**: Determine goals and constraints
2. **Identify alternatives**: Explore different approaches
3. **Risk analysis**: Evaluate and resolve risks
4. **Development**: Build next version of software

### V-Model: Verification and Validation

#### Overview
- **Concept**: Extension of waterfall with testing phases aligned with development phases
- **Shape**: V-shaped diagram showing relationship between development and testing
- **Approach**: Each development phase has corresponding testing phase
- **Focus**: Verification and validation throughout lifecycle

#### Advantages
- **Early defect detection**: Defects identified early in process
- **Systematic approach**: Clear relationship between development and testing
- **Quality focus**: Emphasis on verification and validation
- **Planning**: Testing planned early in development

#### Disadvantages
- **Rigidity**: Inflexible to changes
- **Late discovery**: Issues discovered late in process
- **Documentation**: Heavy documentation requirements
- **Customer involvement**: Limited customer feedback

#### V-Model Phases
- **Requirements** → **Acceptance Testing**
- **System Design** → **System Testing**
- **Architecture Design** → **Integration Testing**
- **Module Design** → **Unit Testing**

### RAD (Rapid Application Development)

#### Overview
- **Concept**: Accelerated development using minimal planning
- **Approach**: Prototyping and iterative development
- **Focus**: Rapid prototyping and user feedback
- **Timeline**: Short development cycles

#### Advantages
- **Speed**: Faster development than traditional methods
- **User involvement**: High user participation
- **Flexibility**: Easy to accommodate changes
- **Prototyping**: Early validation of requirements

#### Disadvantages
- **Requirements**: Requires stable system requirements
- **Team size**: Works best with small teams
- **Technology**: Requires stable technology
- **Documentation**: Less emphasis on documentation

#### RAD Phases
1. **Requirements planning**: Identify system requirements
2. **User design**: User prototypes and feedback
3. **Construction**: Build working model
4. **Cutover**: Implementation and transition

### Iterative and Incremental Models

#### Iterative Model
- **Concept**: Develop software through repeated cycles
- **Approach**: Refine and enhance software through iterations
- **Focus**: Gradually refine requirements and design
- **Benefit**: Incorporate feedback and improvements

#### Incremental Model
- **Concept**: Divide software into increments and develop each increment
- **Approach**: Build and deliver software in parts
- **Focus**: Deliver working software in increments
- **Benefit**: Early delivery of partial functionality

#### Combined Approach
- **Iteration**: Refinement within each increment
- **Increment**: Delivery of working functionality
- **Advantages**: Combines benefits of both approaches
- **Flexibility**: Accommodates changes and delivers value early

### Prototype Model

#### Overview
- **Concept**: Build preliminary version of software to gather requirements
- **Approach**: Create prototype, evaluate, refine requirements
- **Focus**: Requirements validation and user feedback
- **Purpose**: Reduce uncertainty in requirements

#### Types of Prototypes
- **Throwaway**: Used to clarify requirements, discarded
- **Evolutionary**: Starting point for final system
- **Incremental**: Series of prototypes leading to final system

#### Advantages
- **Requirements validation**: Early validation of requirements
- **User feedback**: Direct user involvement and feedback
- **Risk reduction**: Identify issues early
- **Learning**: Better understanding of system requirements

#### Disadvantages
- **Incomplete**: Users may think prototype is final product
- **Time**: May take longer than expected
- **Maintenance**: Prototype code may be difficult to maintain
- **Scope creep**: Users may request additional features

## Agile Frameworks

### Scrum: Sprints, Roles (Product Owner, Scrum Master, Dev Team)

#### Overview
- **Framework**: Lightweight framework for managing complex work
- **Roles**: Product Owner, Scrum Master, Development Team
- **Events**: Sprint, Sprint Planning, Daily Scrum, Sprint Review, Sprint Retrospective
- **Artifacts**: Product Backlog, Sprint Backlog, Increment

#### Scrum Roles

##### Product Owner
- **Responsibility**: Maximize value of product
- **Tasks**: Manage Product Backlog, define requirements, prioritize features
- **Authority**: Sole authority for Product Backlog items
- **Skills**: Domain knowledge, communication, decision-making

##### Scrum Master
- **Responsibility**: Facilitate Scrum process
- **Tasks**: Coach team, remove impediments, facilitate meetings
- **Focus**: Process improvement and team productivity
- **Skills**: Facilitation, coaching, servant leadership

##### Development Team
- **Responsibility**: Deliver potentially shippable increments
- **Size**: 3-9 members
- **Characteristics**: Cross-functional, self-organizing
- **Skills**: All skills necessary to deliver increment

#### Scrum Events

##### Sprint
- **Duration**: 1-4 weeks (usually 2 weeks)
- **Purpose**: Create potentially shippable increment
- **Activities**: All development work occurs during sprint
- **Rule**: No changes that endanger Sprint Goal

##### Sprint Planning
- **Duration**: 8 hours for 1-month sprint
- **Purpose**: Plan work for upcoming sprint
- **Participants**: Entire Scrum Team
- **Outcome**: Sprint Goal and Sprint Backlog

##### Daily Scrum
- **Duration**: 15 minutes
- **Purpose**: Inspect progress and adapt plan
- **Questions**: What did I do yesterday? What will I do today? Any impediments?
- **Focus**: Coordination and communication

##### Sprint Review
- **Duration**: 4 hours for 1-month sprint
- **Purpose**: Inspect increment and adapt Product Backlog
- **Participants**: Scrum Team and stakeholders
- **Outcome**: Updated Product Backlog

##### Sprint Retrospective
- **Duration**: 3 hours for 1-month sprint
- **Purpose**: Inspect team and process, identify improvements
- **Focus**: Continuous improvement
- **Outcome**: Action items for next sprint

### Scrum Ceremonies: Sprint Planning, Daily Standup, Sprint Review, Retrospective

#### Sprint Planning
- **Objective**: Plan work for sprint
- **Inputs**: Product Backlog, latest increment, team capacity
- **Outputs**: Sprint Goal, Sprint Backlog
- **Time-box**: 8 hours for 1-month sprint

#### Daily Standup
- **Objective**: Synchronize activities and plan next 24 hours
- **Format**: Each member answers three questions
- **Focus**: Progress toward Sprint Goal
- **Time-box**: 15 minutes

#### Sprint Review
- **Objective**: Inspect increment and adapt Product Backlog
- **Format**: Demo of completed work
- **Participants**: Scrum Team and stakeholders
- **Time-box**: 4 hours for 1-month sprint

#### Sprint Retrospective
- **Objective**: Improve team processes and dynamics
- **Focus**: What went well, what could be improved, what to try
- **Outcome**: Action items for next sprint
- **Time-box**: 3 hours for 1-month sprint

### Kanban: Visual Workflow, WIP Limits, Continuous Delivery

#### Overview
- **Method**: Visual workflow management system
- **Origin**: Toyota Production System
- **Focus**: Continuous flow and improvement
- **Visualization**: Kanban board with columns

#### Kanban Board
- **Columns**: Represent workflow stages (To Do, In Progress, Done)
- **Cards**: Represent work items
- **WIP Limits**: Maximum number of items in each column
- **Swimlanes**: Horizontal divisions for different types of work

#### Kanban Practices
- **Visualize workflow**: Make work and process visible
- **Limit WIP**: Control amount of work in progress
- **Manage flow**: Optimize flow of work through system
- **Make process policies explicit**: Document workflow rules
- **Implement feedback loops**: Regular meetings to improve process
- **Improve collaboratively**: Continuous improvement culture

#### Benefits
- **Flexibility**: No fixed iterations
- **Continuous delivery**: Work delivered as soon as ready
- **Transparency**: Clear visibility of work status
- **Flow optimization**: Focus on reducing lead time

### Extreme Programming (XP): Pair Programming, TDD

#### Overview
- **Method**: Agile methodology emphasizing technical practices
- **Focus**: Code quality and responsiveness to changing requirements
- **Values**: Communication, simplicity, feedback, courage, respect
- **Practices**: Pair programming, TDD, continuous integration

#### XP Practices

##### Pair Programming
- **Concept**: Two programmers work together at one workstation
- **Roles**: Driver (writes code), Navigator (reviews and thinks strategically)
- **Benefits**: Higher quality code, knowledge sharing, mentoring
- **Challenges**: Requires coordination and communication

##### Test-Driven Development (TDD)
- **Cycle**: Red (write failing test), Green (make test pass), Refactor
- **Approach**: Write tests before implementation code
- **Benefits**: Better design, confidence in changes, living documentation
- **Challenges**: Learning curve, initial time investment

##### Continuous Integration
- **Practice**: Integrate code frequently (multiple times per day)
- **Tools**: Automated build and test systems
- **Benefits**: Early detection of integration issues, quality codebase
- **Requirements**: Automated testing, version control

##### Other XP Practices
- **Small releases**: Deliver working software frequently
- **Simple design**: Keep design simple and clean
- **Refactoring**: Improve code structure without changing behavior
- **Collective ownership**: Anyone can modify any code
- **Coding standards**: Shared coding conventions
- **Sustainable pace**: Maintain consistent work rhythm

### Lean Software Development

#### Overview
- **Origin**: Adaptation of lean manufacturing principles
- **Focus**: Eliminate waste, amplify learning, decide late
- **Principles**: Based on Toyota Production System
- **Goal**: Deliver value efficiently

#### Lean Principles
- **Eliminate waste**: Remove activities that don't add value
- **Amplify learning**: Short feedback loops and experimentation
- **Decide as late as possible**: Keep options open
- **Deliver as fast as possible**: Reduce cycle time
- **Empower the team**: Give autonomy to developers
- **Build integrity in**: Ensure quality throughout process
- **See the whole**: Understand system interactions

#### Waste in Software Development
- **Partially done work**: Work that hasn't delivered value
- **Extra features**: Features not used by customers
- **Relearning**: Relearning forgotten information
- **Handoffs**: Delays and defects from transferring work
- **Delays**: Waiting time in process
- **Task switching**: Context switching overhead
- **Defects**: Time spent fixing bugs

## Testing Methodologies

### Unit Testing, Integration Testing, System Testing

#### Unit Testing
- **Definition**: Testing individual components or units of software
- **Scope**: Individual functions, methods, or classes
- **Purpose**: Verify that each unit works as expected
- **Tools**: JUnit (Java), NUnit (.NET), PyTest (Python)
- **Benefits**: Early bug detection, code quality improvement
- **Best Practices**: Test one thing at a time, use descriptive names

#### Integration Testing
- **Definition**: Testing combined parts of application
- **Scope**: Interaction between modules/components
- **Purpose**: Verify that integrated components work together
- **Approaches**: Top-down, bottom-up, sandwich, big-bang
- **Challenges**: Dependency management, test environment setup
- **Tools**: TestNG, Mockito, WireMock

#### System Testing
- **Definition**: Testing complete and integrated software
- **Scope**: End-to-end functionality of system
- **Purpose**: Verify that system meets requirements
- **Types**: Functional, non-functional, regression testing
- **Environment**: Production-like environment
- **Team**: Usually performed by independent testers

### Acceptance Testing (UAT)

#### Overview
- **Definition**: Formal testing conducted to determine if system satisfies acceptance criteria
- **Purpose**: Verify that system meets business requirements
- **Participants**: End users, customers, stakeholders
- **Timing**: Conducted near end of development cycle

#### Types of Acceptance Testing
- **User Acceptance Testing (UAT)**: Performed by end users
- **Business Acceptance Testing**: Performed by business representatives
- **Contract Acceptance Testing**: Based on contract specifications
- **Regulatory Acceptance Testing**: For regulatory compliance
- **Operational Acceptance Testing**: For operational readiness

#### UAT Process
1. **Planning**: Define scope, criteria, and environment
2. **Test case preparation**: Create realistic scenarios
3. **Execution**: Users execute test scenarios
4. **Defect reporting**: Document issues found
5. **Sign-off**: Approval for system release

### Regression Testing, Smoke Testing

#### Regression Testing
- **Definition**: Testing to ensure that recent changes didn't break existing functionality
- **Purpose**: Verify that software still works after modifications
- **Trigger**: Code changes, bug fixes, enhancements
- **Approach**: Re-run previously passed test cases
- **Automation**: Highly suitable for automation
- **Tools**: Selenium, JUnit, TestNG

#### Smoke Testing
- **Definition**: Preliminary testing to check basic functionality
- **Purpose**: Verify that major functions work before detailed testing
- **Scope**: Critical paths and basic functionality
- **Timing**: Early in testing cycle
- **Duration**: Quick tests (usually 15-30 minutes)
- **Alternative**: Build verification testing

### Performance Testing, Load Testing, Stress Testing

#### Performance Testing
- **Definition**: Testing to determine system performance under various conditions
- **Metrics**: Response time, throughput, resource utilization
- **Purpose**: Ensure system meets performance requirements
- **Types**: Load testing, stress testing, endurance testing

#### Load Testing
- **Definition**: Testing system behavior under expected load
- **Purpose**: Verify system performance under normal conditions
- **Metrics**: Response time, throughput, error rate
- **Tools**: JMeter, LoadRunner, Gatling

#### Stress Testing
- **Definition**: Testing system behavior under extreme conditions
- **Purpose**: Determine system breaking point
- **Approach**: Gradually increase load beyond normal capacity
- **Metrics**: Breaking point, recovery time
- **Focus**: System stability under overload

### Security Testing, Penetration Testing

#### Security Testing
- **Definition**: Testing to identify security vulnerabilities
- **Purpose**: Ensure system protects data and functions properly
- **Types**: Vulnerability scanning, penetration testing, security auditing
- **Focus**: Authentication, authorization, data protection
- **Tools**: OWASP ZAP, Burp Suite, Nessus

#### Penetration Testing
- **Definition**: Simulated cyber attack to find security weaknesses
- **Approach**: Ethical hacking techniques
- **Types**: Black box, white box, gray box testing
- **Deliverables**: Vulnerability report with remediation advice
- **Frequency**: Regular intervals or after major changes

### Test-Driven Development (TDD)

#### Overview
- **Approach**: Write tests before implementation code
- **Cycle**: Red-Green-Refactor
- **Benefits**: Better design, confidence in changes, living documentation
- **Challenges**: Learning curve, initial time investment

#### TDD Process
1. **Write failing test**: Create test that defines desired behavior
2. **Make test pass**: Write minimal code to pass test
3. **Refactor**: Improve code structure without changing behavior
4. **Repeat**: Continue cycle for next functionality

#### Benefits
- **Design**: Encourages simple, testable design
- **Confidence**: Safe refactoring with test safety net
- **Documentation**: Tests document expected behavior
- **Quality**: Early bug detection and prevention

### Behavior-Driven Development (BDD)

#### Overview
- **Approach**: Extend TDD with natural language specifications
- **Focus**: Business-readable specifications
- **Tools**: Cucumber, SpecFlow, JBehave
- **Language**: Given-When-Then format

#### BDD Process
- **Collaboration**: Business, developers, testers work together
- **Specifications**: Written in business-readable format
- **Automation**: Specifications become automated tests
- **Living documentation**: Tests serve as documentation

#### Given-When-Then Format
- **Given**: Set up initial context
- **When**: Describe action or event
- **Then**: Describe expected outcome

## DevOps Practices

### CI/CD Pipelines: Jenkins, GitLab CI, GitHub Actions

#### Continuous Integration (CI)
- **Definition**: Practice of merging code changes frequently
- **Frequency**: Multiple times per day
- **Process**: Code commit → Build → Test → Report
- **Benefits**: Early bug detection, reduced integration conflicts
- **Tools**: Jenkins, GitLab CI, GitHub Actions, Travis CI

#### Continuous Delivery (CD)
- **Definition**: Extends CI to ensure code is deployable at any time
- **Process**: CI process + automated deployment preparation
- **Benefits**: Faster delivery, reduced deployment risk
- **Prerequisites**: Automated testing, infrastructure as code

#### Continuous Deployment
- **Definition**: Fully automated deployment to production
- **Process**: Code commit → Build → Test → Deploy
- **Benefits**: Fastest delivery, immediate value to users
- **Requirements**: Comprehensive automation and monitoring

#### CI/CD Pipeline Components
- **Source Control**: Git repositories
- **Build Tools**: Maven, Gradle, MSBuild
- **Testing**: Unit, integration, acceptance tests
- **Packaging**: Create deployable artifacts
- **Deployment**: Automate deployment process
- **Monitoring**: Track deployment and application health

#### Popular CI/CD Tools

##### Jenkins
- **Type**: Open-source automation server
- **Features**: Plugin ecosystem, pipeline as code
- **Architecture**: Master-slave architecture
- **Flexibility**: Highly customizable

##### GitLab CI
- **Type**: Integrated with GitLab
- **Features**: Built-in CI/CD, container registry
- **Pipeline**: Defined in .gitlab-ci.yml
- **Integration**: Seamless with GitLab projects

##### GitHub Actions
- **Type**: Integrated with GitHub
- **Features**: Workflow automation, marketplace
- **Workflow**: Defined in YAML files
- **Integration**: Tight integration with GitHub

### Infrastructure as Code: Terraform, CloudFormation

#### Overview
- **Concept**: Managing and provisioning infrastructure through code
- **Approach**: Version-controlled, testable, repeatable infrastructure
- **Benefits**: Consistency, automation, collaboration
- **Tools**: Terraform, CloudFormation, Ansible

#### Infrastructure as Code Benefits
- **Version control**: Track infrastructure changes
- **Reproducibility**: Consistent environments
- **Automation**: Reduce manual errors
- **Collaboration**: Share and review infrastructure code
- **Testing**: Test infrastructure changes before deployment

#### Terraform
- **Provider**: Multi-cloud support (AWS, Azure, GCP, etc.)
- **Language**: HashiCorp Configuration Language (HCL)
- **State management**: Tracks resource state
- **Modules**: Reusable infrastructure components

#### AWS CloudFormation
- **Provider**: Amazon Web Services
- **Language**: JSON or YAML templates
- **Integration**: Deep AWS service integration
- **Change sets**: Preview changes before execution

#### Ansible
- **Approach**: Agentless configuration management
- **Language**: YAML playbooks
- **Push model**: Executes from control node
- **Idempotency**: Safe to run multiple times

### Configuration Management: Ansible, Puppet, Chef

#### Overview
- **Purpose**: Automate configuration and management of systems
- **Goal**: Maintain consistent system state
- **Approach**: Define desired state in code
- **Benefits**: Reduce manual errors, ensure consistency

#### Ansible
- **Architecture**: Agentless, uses SSH
- **Language**: YAML playbooks
- **Inventory**: Defines managed systems
- **Modules**: Reusable automation components
- **Push model**: Executes from control node

#### Puppet
- **Architecture**: Agent-server model
- **Language**: Puppet DSL
- **Manifests**: Define system configuration
- **Catalog**: Compiled configuration applied to systems
- **Pull model**: Agents check in periodically

#### Chef
- **Architecture**: Agent-server model
- **Language**: Ruby-based DSL
- **Recipes**: Define configuration steps
- **Cookbooks**: Collections of recipes
- **Run-list**: Ordered list of recipes to execute

### Containerization: Docker, Kubernetes

#### Docker
- **Purpose**: Platform for developing, shipping, and running applications
- **Containers**: Lightweight, portable, self-sufficient packages
- **Images**: Templates for creating containers
- **Dockerfile**: Instructions for building images
- **Benefits**: Consistency, portability, resource efficiency

#### Kubernetes
- **Purpose**: Container orchestration platform
- **Features**: Scaling, load balancing, service discovery
- **Architecture**: Master-worker nodes
- **Objects**: Pods, Services, Deployments, ConfigMaps
- **Benefits**: High availability, scalability, self-healing

#### Container Orchestration Concepts
- **Scaling**: Automatically adjust number of containers
- **Load balancing**: Distribute traffic across containers
- **Service discovery**: Containers find each other
- **Health checks**: Monitor container health
- **Rolling updates**: Deploy new versions without downtime

### Monitoring and Logging: Prometheus, ELK Stack

#### Monitoring
- **Purpose**: Track system performance and health
- **Metrics**: CPU, memory, disk, network usage
- **Alerting**: Notify when thresholds exceeded
- **Dashboards**: Visualize system performance

#### Prometheus
- **Type**: Time-series database
- **Collection**: Pull-based metric collection
- **Query language**: PromQL
- **Alerting**: Built-in alerting rules
- **Ecosystem**: Rich set of exporters and integrations

#### ELK Stack
- **Components**: Elasticsearch, Logstash, Kibana
- **Elasticsearch**: Search and analytics engine
- **Logstash**: Data processing pipeline
- **Kibana**: Data visualization dashboard
- **Beats**: Lightweight data shippers

#### Monitoring Best Practices
- **Measure what matters**: Focus on business metrics
- **Set appropriate thresholds**: Avoid alert fatigue
- **Context-rich alerts**: Include relevant information
- **Automated responses**: Respond to common issues automatically
- **Historical analysis**: Track trends over time

## Version Control

### Git Commands: clone, commit, push, pull, branch, merge, rebase

#### Basic Git Commands

##### clone
- **Purpose**: Create local copy of remote repository
- **Usage**: `git clone <repository-url>`
- **Result**: Creates local repository with all history

##### commit
- **Purpose**: Save changes to local repository
- **Usage**: `git commit -m "commit message"`
- **Prerequisites**: Files must be staged with `git add`

##### push
- **Purpose**: Upload local commits to remote repository
- **Usage**: `git push origin <branch-name>`
- **Result**: Makes changes available to others

##### pull
- **Purpose**: Download and integrate changes from remote repository
- **Usage**: `git pull origin <branch-name>`
- **Equivalent**: `git fetch` + `git merge`

#### Branching Commands

##### branch
- **Purpose**: Create, list, or delete branches
- **Usage**: 
  - `git branch` (list branches)
  - `git branch <branch-name>` (create branch)
  - `git branch -d <branch-name>` (delete branch)

##### merge
- **Purpose**: Combine changes from different branches
- **Usage**: `git merge <source-branch>`
- **Result**: Creates merge commit combining changes

##### rebase
- **Purpose**: Apply changes from one branch onto another
- **Usage**: `git rebase <base-branch>`
- **Result**: Creates linear history by replaying commits

#### Advanced Git Commands

##### stash
- **Purpose**: Temporarily save changes without committing
- **Usage**: `git stash`, `git stash pop`
- **Benefit**: Clean working directory for other tasks

##### cherry-pick
- **Purpose**: Apply specific commit to current branch
- **Usage**: `git cherry-pick <commit-hash>`
- **Benefit**: Selective application of changes

##### reset
- **Purpose**: Undo changes in different ways
- **Types**: `--soft`, `--mixed`, `--hard`
- **Caution**: Can permanently lose changes

### Branching Strategies: Git Flow, GitHub Flow, Trunk-Based Development

#### Git Flow
- **Branches**: master, develop, feature, release, hotfix
- **Master**: Production-ready code
- **Develop**: Integration branch for features
- **Feature**: Individual features
- **Release**: Prepare for release
- **Hotfix**: Urgent fixes to production
- **Benefits**: Clear separation of concerns
- **Drawbacks**: Complex for small teams

#### GitHub Flow
- **Branches**: master, feature branches
- **Master**: Always deployable
- **Process**: Create branch → Commit changes → Open PR → Code review → Merge → Deploy
- **Benefits**: Simple, continuous deployment
- **Drawbacks**: Less formal release process

#### Trunk-Based Development
- **Branches**: Single main branch (master/trunk)
- **Commits**: Small, frequent commits to main branch
- **Testing**: Comprehensive automated testing
- **Benefits**: Reduced merge conflicts, faster feedback
- **Drawbacks**: Requires strong testing discipline

### SVN (Subversion) Basics

#### Overview
- **Type**: Centralized version control system
- **Architecture**: Client-server model
- **Repository**: Central server stores all history
- **Checkout**: Working copy on local machine
- **Commit**: Send changes to central repository

#### SVN vs Git
- **Centralized vs Distributed**: SVN centralized, Git distributed
- **Branching**: SVN lightweight, Git more flexible
- **Offline work**: SVN requires connection, Git works offline
- **History**: SVN linear, Git has branching history

#### SVN Commands
- `svn checkout`: Get working copy
- `svn update`: Get latest changes
- `svn add`: Add files to version control
- `svn commit`: Send changes to repository
- `svn status`: Show file status
- `svn log`: Show commit history

## Documentation

### Technical Specifications

#### Purpose
- **Communication**: Share technical details with team
- **Reference**: Document system architecture and design
- **Maintenance**: Guide for future development
- **Knowledge transfer**: Onboard new team members

#### Types of Technical Specs
- **System architecture**: High-level system design
- **API documentation**: Interface specifications
- **Database schema**: Data structure definitions
- **Deployment guide**: Environment setup instructions
- **Integration specs**: System interaction details

#### Best Practices
- **Keep current**: Update with code changes
- **Be specific**: Include examples and diagrams
- **Use templates**: Consistent format across team
- **Review process**: Peer review before finalization
- **Version control**: Track specification changes

### API Documentation

#### Importance
- **Developer experience**: Enable easy API consumption
- **Integration**: Facilitate system integration
- **Maintenance**: Guide for API evolution
- **Testing**: Basis for API testing

#### Documentation Tools
- **Swagger/OpenAPI**: Interactive API documentation
- **Postman**: API documentation and testing
- **Javadoc/Sphinx**: Language-specific tools
- **GitBook/Confluence**: Documentation platforms

#### API Documentation Elements
- **Endpoints**: URLs and HTTP methods
- **Parameters**: Request parameters and headers
- **Responses**: Expected response format
- **Examples**: Sample requests and responses
- **Error codes**: Possible error responses
- **Authentication**: Security requirements

### User Manuals and Guides

#### User Manual Types
- **Getting started**: Quick introduction to software
- **Feature guides**: Detailed instructions for features
- **Troubleshooting**: Solutions to common problems
- **FAQ**: Answers to frequently asked questions

#### Best Practices
- **User-focused**: Address user needs and goals
- **Step-by-step**: Clear, sequential instructions
- **Visual aids**: Screenshots and diagrams
- **Accessible**: Plain language, avoid jargon
- **Regular updates**: Keep current with software changes

### Code Comments and Inline Documentation

#### Comment Types
- **File headers**: Overall file purpose and author
- **Function comments**: Purpose, parameters, return values
- **Inline comments**: Explain complex logic
- **TODO/FIXME**: Track future work

#### Documentation Standards
- **Language-specific**: Follow conventions (Javadoc, docstrings)
- **Consistency**: Uniform style across codebase
- **Brevity**: Concise but informative
- **Accuracy**: Keep comments synchronized with code

## Requirements Engineering

### Functional vs Non-Functional Requirements

#### Functional Requirements
- **Definition**: What the system should do
- **Examples**: User authentication, data processing, report generation
- **Characteristics**: Observable behavior, testable
- **Documentation**: Use cases, user stories, functional specifications

#### Non-Functional Requirements
- **Definition**: How the system should perform
- **Examples**: Performance, security, usability, reliability
- **Characteristics**: Quality attributes, constraints
- **Documentation**: Quality attributes, service level agreements

#### Examples
- **Functional**: "System shall allow users to log in with username and password"
- **Non-Functional**: "System shall authenticate users within 2 seconds"

### Use Case Analysis

#### Overview
- **Purpose**: Describe system functionality from user perspective
- **Actors**: Users or external systems interacting with system
- **Scenarios**: Specific sequences of interactions
- **Benefits**: Clear understanding of system behavior

#### Use Case Components
- **Title**: Brief description of use case
- **Actor**: Who performs the use case
- **Preconditions**: Conditions before use case starts
- **Main flow**: Primary sequence of steps
- **Alternative flows**: Exception scenarios
- **Postconditions**: State after use case completes

#### Use Case Diagrams
- **Actors**: Stick figures representing users/external systems
- **Use cases**: Ovals representing system functions
- **Relationships**: Lines showing interactions
- **Extends**: Optional functionality
- **Includes**: Mandatory functionality

### Requirements Elicitation Techniques

#### Interviews
- **Approach**: One-on-one conversations with stakeholders
- **Benefits**: Detailed information, clarification possible
- **Challenges**: Time-consuming, potential bias
- **Best practices**: Prepare questions, take notes, confirm understanding

#### Surveys/Questionnaires
- **Approach**: Structured questions to multiple stakeholders
- **Benefits**: Reach many people, quantitative data
- **Challenges**: Limited depth, low response rate
- **Best practices**: Clear questions, appropriate sample size

#### Observation
- **Approach**: Watch users performing tasks
- **Benefits**: Real behavior, identify pain points
- **Challenges**: Hawthorne effect, ethical considerations
- **Best practices**: Respect privacy, take detailed notes

#### Workshops
- **Approach**: Collaborative sessions with multiple stakeholders
- **Benefits**: Diverse perspectives, consensus building
- **Challenges**: Coordination, dominant voices
- **Best practices**: Skilled facilitation, structured agenda

#### Prototyping
- **Approach**: Create preliminary version to validate requirements
- **Benefits**: Early feedback, visual representation
- **Challenges**: Expectation management
- **Best practices**: Clear communication about prototype status

## Summary

This chapter covered essential software development methodologies that are crucial for managing software projects effectively. Understanding these methodologies helps in selecting appropriate approaches for different scenarios and making informed decisions about technology investments. The next chapter will focus on cloud computing and virtualization technologies.

## Key Takeaways

1. Different SDLC models suit different project types and requirements
2. Agile methodologies emphasize flexibility and customer collaboration
3. Testing methodologies ensure software quality at different levels
4. DevOps practices integrate development and operations for faster delivery
5. Version control is essential for collaborative development
6. Proper documentation supports maintainability and knowledge transfer
7. Requirements engineering establishes clear project foundations

## Practice Questions

1. What are the main differences between Waterfall and Agile methodologies?
2. Explain the three roles in Scrum and their responsibilities.
3. What is the difference between continuous delivery and continuous deployment?
4. Name three types of testing and their purposes.
5. What does the acronym TDD stand for and what is its process?

## Answers

1. Waterfall is sequential with distinct phases and heavy documentation, while Agile is iterative with frequent releases and emphasizes flexibility and customer collaboration.
2. Product Owner (maximizes product value), Scrum Master (facilitates Scrum process), Development Team (delivers potentially shippable increments).
3. Continuous delivery ensures code is deployable at any time, while continuous deployment automatically deploys code to production without human intervention.
4. Unit testing (individual components), Integration testing (component interactions), System testing (complete system functionality).
5. TDD stands for Test-Driven Development, and its process is Red (write failing test), Green (make test pass), Refactor (improve code structure).