# Development Approach and Methodology

Status: **Planned approach**. The activities below describe intended work, not completed prototypes, Sprints, or implementation.

**Project:** Restaurant Service System

**Software Lifecycle Model:** Rapid Prototyping

**Software Development Methodology:** Scrum

Our project is a Restaurant Service System that allows customers to search for restaurants, book tables, pre-order food, make payments, and call waiters through their smartphones. The system also provides restaurant staff with tools for managing reservations, orders, and table availability. We selected **Rapid Prototyping** as our lifecycle approach and **Scrum** as our development methodology because our project requires flexible development, user feedback, and efficient teamwork.

## **Software Lifecycle Model – Rapid Prototyping**

Rapid Prototyping involves creating early versions of a system to validate requirements, test functionality, and collect user feedback before full implementation.

### **Why Rapid Prototyping?**

- **Unclear Requirements:** Some requirements are not fully defined, such as reservation modification rules, staff functionality, and integration details. Prototypes help us clarify them before implementation  
-  **User Interface Complexity:** Our system includes an interactive restaurant floor plan, table selection, menus, and ordering interfaces. Prototyping allows us to test their usability and improve the user experience  
- **Different User Roles:** Customers, waiters, and restaurant managers have different needs. Prototypes allow us to evaluate their workflows and collect feedback from representative users  
- **Limited Resources:** We have limited time and development resources. Identifying design problems during prototyping is less expensive than rewriting fully implemented functionality  
- **Early Validation:** We can quickly demonstrate restaurant search, table booking, and pre-ordering without implementing complex payment and POS integrations immediately

### **How We Will Apply Rapid Prototyping**

1. Identify the main requirements and user scenarios.  
2. Create interactive prototypes of the customer and staff interfaces.  
3. Test the prototypes and collect feedback.  
4. Improve the designs based on the results.  
5. Use the validated requirements to guide full implementation.

Rapid Prototyping is especially useful during the requirements and design stages. Since it is not a complete standalone lifecycle model, we plan to follow prototyping with incremental implementation of the production system.

## **Software Development Methodology – Scrum**

Scrum is an Agile framework that organizes development into short iterations called Sprints. We selected Scrum because it supports flexible planning, regular feedback, and collaboration within a small team.

### **Why Scrum?**

- **Small Team:** Our team consists of three developers and one tester. Scrum supports direct communication, shared responsibility, and flexible task distribution without complex management structures  
- **Limited Professional Experience:** Regular planning, reviews, and retrospectives help us identify problems and improve our workflow  
- **Changing Requirements:** Restaurant owners, employees, and customers may request changes after reviewing prototypes. Scrum allows us to update priorities between Sprints  
- **Limited Time:** We need to balance project development with university studies. Short Sprints help us set realistic goals, monitor progress, and prioritize essential features  
-  **Continuous Testing.** Having a dedicated tester allows us to validate features throughout development. Developers also participate in testing, helping us detect defects early.

### **How We Will Apply Scrum**

We propose two-week Sprints.

* Product Backlog: Prioritized features and requirements.  
* Sprint Planning: Select tasks and define the Sprint Goal.  
* Daily Scrum: Short meetings to coordinate work and identify obstacles.  
* Sprint Review: Demonstrate completed functionality and collect feedback.  
* Sprint Retrospective: Discuss improvements to our development process.

Scrum will be used during both prototyping and full implementation.

## **Justification Based on Project Characteristics**

| Criterion | Rapid Prototyping | Scrum |
| :---- | :---- | :---- |
| **1\. Product / Project Type** | Our restaurant platform has multiple user interfaces and workflows that should be validated before implementation | Helps manage requirements from customers, waiters, and restaurant managers |
| **2\. Project Scale** | The system has several modules: reservations, ordering, payments, and recommendations. We can prototype the most important features first | Allows us to divide a medium-complexity project into manageable Sprints |
| **3\. Team Size** | Four people can create, evaluate, and improve prototypes quickly | Suitable for our small team of three developers and one tester, with direct communication and minimal hierarchy |
| **4\. Team Competence** | As third-year students, we can validate design decisions before implementing unfamiliar functionality | Regular reviews and collaboration help us develop skills and share knowledge |
| **5\. Business Factors** | Early validation reduces the risk of spending limited resources on unnecessary features | Lightweight management, flexible priorities, and short iterations fit our academic schedule |
| **6\. Artifacts Necessity** | Requires prototypes, use cases, feedback records, and validated requirements | Uses Product Backlog, Sprint Backlog, and Increment, supported by architecture documentation and test reports |
| **7\. Technological Factors** | Allows us to test interface concepts and simulate interactions with payment and POS systems before full integration | Supports planning technical tasks, regular integration, testing, and resolving implementation problems |
