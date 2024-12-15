---
layout: essay
type: essay
title: "Confusion to Confidence All Thanks to AI"
# All dates must be YYYY-MM-DD format!
date: 2024-12-14
published: true
labels:
  - Artificial Intelligence
  - TypeScript
  - Software Development
---

# Reflection on AI Usage in ICS 314

<br>

### I. Introduction

Starting ICS 314, I felt overwhelmed observing the coding experience my classmates possessed. When Professor Port encouraged us to use AI tools, it opened new possibilities for approaching the coursework. I began with ChatGPT, as it was what I was familiar with and the most widely known option, but I later discovered Claude, which proved more effective with complex tasks essential for our later projects. The integration of these AI tools fundamentally changed my approach to learning software development.

<br>

### II. Personal Experience with AI

##### 1. Experience WODs
The initial WODs presented significant challenges, particularly the Prisma assignments. When faced with structuring database schemas, I turned to ChatGPT for guidance. While the generated code required modifications to meet our specific requirements, it provided valuable starting points. The ability to ask the AI about its code choices enhanced my understanding of database design principles and helped me grasp the underlying concepts.

##### 2. In-class Practice WODs
I developed a methodical approach to practice WODs, attempting solutions independently before consulting AI for specific challenges. This strategy balanced skill development with efficient problem-solving. Occasionally, I would complete entire practice WODs without AI assistance to validate my understanding. These self-imposed challenges, while demanding, confirmed my growing competence in software development. I didn't feel any pressure since these in-class WODs were not penalized for hitting DNF times.

##### 3. In-class WODs
In-class WODs introduced time pressure that initially affected my performance. Using AI as a resource helped me maintain focus on problem-solving rather than racing against the clock. Though the AI-generated solutions weren't always perfect, they served as foundations I could refine based on concepts learned in class. This approach helped me consistently complete assignments within the allocated time while deepening my understanding of the material. For the first couple of WODs I would directly copy and paste the assignment instructions into ChatGPT and it did a decent job at generating functioning code. They always required refinement but they were the most time effective way to make sure that I didn't hit any DNF times.

##### 4. Essays
Technical writing presented unique challenges in organizing and articulating complex concepts. I developed a process of initial brainstorming followed by AI-assisted organization. This method preserved my original insights while creating coherent, well-structured documents. The AI helped identify areas needing additional explanation, improving the overall quality of my technical documentation.

##### 5. Final Project
The final project demonstrated the distinct capabilities of different AI tools. Claude excelled at handling complex development challenges, particularly with Next.js authentication and Prisma database connectivity. When implementing the check-in system for monitoring location occupancy, Claude provided detailed explanations of the averaging algorithm and database integration. This guidance facilitated not just implementation, but comprehensive understanding of the system architecture.

##### 6. Learning Concepts / Tutorials
AI transformed my approach to learning new concepts by creating a space for unlimited inquiry. The ability to ask repeated questions about complex topics without concern for time constraints or judgment enhanced my understanding significantly. When facing challenges with Next.js 14 guidelines and ESLint configurations, I engaged in detailed discussions with AI to understand best practices. This resource proved invaluable when documentation or tutorials didn't align with our current software versions or fell outside of class materials.

##### 7. Class/Discord Participation
As someone new to programming, I initially hesitated to participate in class discussions or Discord channels where many peers had substantial coding experience. AI helped bridge this knowledge gap by allowing me to validate my understanding before contributing. This preparation increased my confidence in participating in technical discussions and helped me overcome the initial intimidation of not understanding "simple topics".

##### 8. Asking or Answering Smart Questions
The process of formulating smart questions improved significantly with AI assistance. When our team encountered deployment issues with Vercel, I used AI to refine my questions about Next.js authentication and Prisma database connectivity. This preparation helped me present issues more clearly in when talking directly with Professor Port in class, leading to more productive problem-solving discussions. We were able to troubleshoot and found out that the issue had to do with correctly setting up the environment files and NeonDB.

##### 9. Coding Examples
AI excelled at providing diverse implementations of coding concepts. When learning new functions or features, I would request multiple approaches to understand the full range of possibilities. For example, when implementing the business indicator feature, AI demonstrated various methods for data aggregation and display. I was able to iterate on each method to dissect each part of each line of code, helping me select the most efficient solution for our specific needs.

##### 10. Explaining Code
Understanding and explaining code became significantly more manageable with AI assistance. During our final project development, I frequently used AI to break down complex functions into understandable components. For example, when implementing the location check-in system, AI helped dissect each part of the business indicator algorithm, explaining how it collected user inputs, calculated averages, and displayed results. The AI's ability to explain code at different levels of detail proved invaluable - I could request high-level overviews or detailed line-by-line explanations depending on my needs. This helped me not only understand the code but also explain it effectively to my team members during collaboration.

##### 11. Writing Code
The distinction between AI tools became apparent in code generation tasks. While ChatGPT handled basic implementations effectively, Claude demonstrated superior capabilities in generating complex code structures. When developing user interfaces, it was able to accurately translate our mockups into functional components. All of the generated code still required careful review and customization to meet our specific requirements but Claude was able to so an amazing job with just images.

##### 12. Documenting Code
AI streamlined the documentation process while revealing an interesting challenge: the generated comments often needed humanization. The AI produced comprehensive documentation, but I found myself regularly adjusting the language to achieve a more natural, maintainable style. This process helped me develop my own documentation voice while maintaining technical accuracy.

##### 13. Quality Assurance
Debugging complex applications revealed both the strengths and limitations of AI assistance. I was able to debug and trouble shoot most of my issues by copying and pasting my error messages into AI prompts. While it efficiently resolved common issues and ESLint violations, complex problems involving database connections and state management, required traditional debugging approaches. This highlighted the importance of maintaining strong fundamental debugging skills alongside AI utilization.

##### 14. Other Uses in ICS 314
AI proved instrumental in the initial planning and architecture phases of our final project. When conceptualizing our study spot finder application, I asked AI to analyze potential challenges and complexities we might encounter. The AI identified several critical considerations we hadn't initially thought of:

  1. Real-time occupancy tracking would require careful database design to handle concurrent updates and prevent race conditions
  2. Peak hours tracking would need historical data aggregation and efficient storage solutions
  3. Noise level reporting would benefit from a time-decay algorithm to prioritize recent reviews
  4. User authentication would need special handling for different user types (students vs. spot owners)
  5. Search functionality would require geospatial indexing for efficient location-based queries

This foresight helped us structure our development timeline more effectively, prioritize what we wanted to implement, and allowed us to starting with the most challenging mvp components. The AI also suggested breaking our application into key components:

  - User Management System
  - Location Database with Geospatial Indexing
  - Review and Rating System
  - Real-time Occupancy Tracker
  - Study Spot Search Engine
  - Notification System for Peak Hours

This organizational structure helped us divide tasks among team members and establish clear interfaces between different parts of the application. The AI's suggestions for project organization proved particularly valuable during the implementation phase, as we had already considered many edge cases and potential bottlenecks before writing any code.

<br>

### III. Impact on Learning and Understanding
The integration of AI in my learning process created an interesting balance between efficiency and fundamental skill development. While AI accelerated my ability to implement complex features, it occasionally reduced my focus on syntax memorization. The trade-off enabled deeper exploration of architectural concepts and system design principles. The time saved on implementation details allowed me to focus on understanding larger software engineering concepts and best practices.

### IV. Practical Applications
Beyond ICS 314, I've applied AI tools in developing personal projects ranging from custom Spotify integrations to Discord bots. These applications demonstrated AI's value in real-world development scenarios. The experience gained in effectively utilizing AI for academic projects translated directly to independent development work, enhancing both productivity and learning outcomes. I've become particularly interested in AI's potential for UX/UI design and rapid prototyping and will continue to explore it outside of ICS 314.

### V. Challenges and Opportunities
Working with AI revealed specific challenges in handling complex project structures and maintaining consistent code organization across multiple files. These limitations often required creative solutions and deeper understanding of system architecture that I found ChatGPT struggled with. These challenges also present opportunities to develop stronger problem-solving skills and better grasp the importance of modular design principles and the importance of understanding software without the help of AI.

### VI. Comparative Analysis
The combination of traditional instruction and AI assistance created a comprehensive learning environment. While classroom instruction provided essential theoretical foundations, AI enabled practical application and experimentation with concepts. I was able to use it as a way to experiment with the code that it generated. This dual approach supported different learning styles and allowed for more thorough exploration of complex topics than either method could provide alone.

### VII. Future Considerations
As AI tools continue to evolve, their role in software development will expand beyond code generation to potentially reshape entire development workflows. Understanding how to effectively integrate these tools while maintaining code quality and security has become crucial. The experience gained in ICS 314 has prepared me to thoughtfully incorporate AI into future development work while maintaining strong fundamental programming skills.

### VIII. Conclusion
My experience with AI in ICS 314 has demonstrated the transformative potential of these tools in software engineering education. While AI significantly enhanced my learning and development capabilities, it also highlighted the importance of maintaining strong fundamental skills and understanding core concepts. The course has prepared me to leverage AI tools effectively while remaining mindful of their limitations and security implications. I would love to explore the security concerns that utilizing AI has in professional applications and how to use it safely when dealing with sensitive data. As I move forward in software development, I am confident and excited in my ability to balance AI assistance with independent problem-solving skills, creating more efficient and innovative solutions.