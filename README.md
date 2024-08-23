<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://user-images.githubusercontent.com/25423296/163456776-7f95b81a-f1ed-45f7-b7ab-8fa810d529fa.png">
  <source media="(prefers-color-scheme: light)" srcset="https://user-images.githubusercontent.com/25423296/163456779-a8556205-d0a5-45e2-ac17-42d089e3c3f8.png">
  <img alt="Shows an illustrated sun in light mode and a moon with stars in dark mode." src="https://user-images.githubusercontent.com/25423296/163456779-a8556205-d0a5-45e2-ac17-42d089e3c3f8.png">
</picture>

# Clean-Code-Notes
- This repository contains a concise summary of the book "Clean Code in JavaScript" by James Padolsey. It compiles the core ideas, key points, and essential principles from each chapter of the book. The summary is intended to provide a quick reference to the most important concepts without the need to reread the entire book.

### Section 1: What is Clean Code Anyway?

## Chapter 1: Setting the Scene

<details>
  <summary>JavaScript Origins</summary>
  
  - Created by Brendan Eich in 1995 as a "glue language" to manipulate HTML via the DOM API.
  - Grew from simple web scripts to a key language for complex web applications, server runtimes (Node.js), and more.

</details>

<details>
  <summary>Evolution</summary>
  
  - Grew from simple web scripts to a key language for complex web applications, server runtimes (Node.js), and more.
  - JavaScript was standardized as ECMAScript in 1997, with ongoing updates from the TC39 committee.

</details>

<details>
  <summary>Community and Challenges</summary>
  
  - The JavaScript ecosystem is vast, with numerous frameworks and tools, leading to challenges in writing clean, maintainable code.

</details>

<details>
  <summary>Purpose of Code</summary>
  
  - Code serves as a problem-solving tool and a form of communication, expressing intent with specificity.

</details>

<details>
  <summary>Importance of Users</summary>
  
  - Understanding the needs of users (both developers and end-users) is critical to writing effective, reliable code.

</details>

<details>
  <summary>What is the Problem?</summary>

  We've spoken about the importance of the user in programming, and how we must first understand what it is they wish to do if we are to have any hope of helping them.
  
  Only by understanding the problem can we begin to assemble requirements that our code will have to fulfill. In the exploration of the problem, it's useful to ask yourself the following questions:
  
  - What problem is the user encountering?
  - How do they currently carry out this task?
  - What existing solutions are there and how do they work?
  
  When we have assembled a complete understanding of the problem, we can then begin ideating, planning, and writing code to solve it. At each step, often without realizing it, we will be modeling the problem in a way that makes sense to us. The way we think about the problem will have a drastic effect on the solution we end up creating. The model of the problem we create will dictate the code we end up writing.

</details>

<details>
  <summary>What is the Model of a Problem?</summary>

  - A model or conceptual model is a schematic or representation that describes how something works. We create and adapt models all the time without realizing it. Over time, as you gain more information about a problem domain, your model will improve to better match reality.
  
  **Example:** Imagine we are responsible for a note-taking application for students. A user has expressed the following problem:
  
  "I have many notes for my studies and so am finding it hard to organize them. Specifically, when trying to find a note on a given topic, I'll try to use the Search feature but I rarely find what I'm looking for since I can't always recall the specific text I wrote."
  
  There are a few options we could explore:
  
  - **Categories:** Hierarchical folder structure for categories.
  - **Tags:** Ability to tag a note with one or more words or phrases.
  - **Links:** Introduce a linking feature so notes can link to other notes that are related.
  
  Each solution has its pros and cons and will affect how users end up using the application.

</details>

<details>
  <summary>Truly Understanding the Problem Domain</summary>

  - The first point of failure is typically misunderstanding the problem. If we don't understand what users are truly trying to accomplish, and we have not received all requirements, then we will inevitably retain a bad model of the problem and thus end up implementing the wrong solutions.

  **Example:** Imagine that this scenario occurs at some point before the invention of the kettle:

  *Susanne (engineer):* Matt, we've been asked to design a vessel that users can boil water with.

  *Matthew (engineer):* Understood; I will create a vessel that does exactly that.
  
  - Matthew asks no questions and immediately gets to work. One day later, he comes up with a contraption without a handle, which he later adds after receiving feedback. This miscommunication could have been avoided by better understanding the user's needs from the beginning.

</details>

<details>
  <summary>Writing Code for Humans</summary>

  - This entire book is concerned with teaching you how to write clean code in JavaScript. Writing code for humans is broadly about the clarity of intent, while writing code for machines is broadly about functionality. These needs cross over, but it's vital to discern the difference.

</details>

<details>
  <summary>Readability</summary>

 - When we write code, it's essential to consider how human brains will consume it. Fellow programmers will scan over your code, reading the pertinent parts, attempting to gain a running comprehension of its inner workings. Readability is the first hurdle that they must overcome. If they are unable to read and cognitively navigate the code you've written, then they'll be less able to use it. This will drastically limit the utility and value of your code.

- Programmers, in my experience, don't tend to like thinking of code in terms of aesthetic design, but the best programmers will appreciate that these concepts are intrinsically intertwined. The design of our code in a presentational or visual sense is as vital to its comprehensibility as its architectural design. Design, in the end, is about creating something in a way that optimally delivers a purpose for its users. For our fellow programmers, that purpose is comprehension. And so we must design our code to deliver that purpose.

- Machines care purely about specifications and will parse valid code into its parts with little effort. Humans, however, are more complex. We are less capable in areas where machines excel, hence their existence, but we are also skillful in areas where machines may falter. Our highly evolved brains, among their many talents, have become incredibly skilled at spotting patterns and inconsistencies. We rely on difference, or contrast, to focus our attention. If a pattern is not being followed, then it creates more work for our brains. For an example of such inconsistency, have a look at this code:

</details>

<details>
  <summary>Meaningful abstractions</summary>
  
- Abstraction simplifies complexity by presenting it in a more understandable form. In coding, abstractions allow us to manage complexity without needing to grasp all underlying details. For example, JavaScript abstracts memory management, and browsers abstract HTTP and HTML details, making technology easier to use. The key is that every line of code involves using, creating, or communicating abstractions.
  ![Screenshot_1](https://github.com/user-attachments/assets/4909a76c-53fc-4e42-854d-11d45ab8a3a0)

</details>

<details>
  <summary>The Tower of Abstraction</summary>
  
- The tower of abstraction represents the layers of complexity in technology, from hardware (transistors, memory) at the base to high-level interfaces (browsers, JavaScript) at the top. Each layer abstracts complexity for the layer above. When writing code, we're adding to this tower, with users either being other developers or end-users who interact with the simplified interfaces we've built. This analogy highlights the dependency on each layer functioning correctly and the fragility of the entire system.
 ![Screenshot_2](https://github.com/user-attachments/assets/5520edc6-e8b8-4131-95fa-8dc58d5ce3c0)

</details>

<details>
  <summary>The Layers of Clean Code</summary>
  
- The book will build on foundational concepts to explore clean code abstractions, from reliable and usable software to detailed JavaScript syntax. By the end, you'll understand multiple layers of clean code, ranging from individual lines to overall architectural design.

</details>

<details>
  <summary>Summary</summary>
  
- This chapter establishes a foundation for writing effective code by emphasizing the importance of understanding user needs, problem domains, and clear communication of intent. It highlights the significance of readability and meaningful abstractions. The next chapter will delve into the tenets of clean code—reliability, efficiency, maintainability, and usability—applying these principles to JavaScript.

</details>

## Chapter 2: The Tenets of Clean Code

- This chapter focuses on the four core tenets of clean code: reliability, efficiency, maintainability, and usability. These tenets are essential for creating high-quality software. They are not strict rules but rather perspectives through which to evaluate your code. The chapter will use analogies and JavaScript examples to illustrate each tenet and show how to apply them to improve your code.
  
<details>
  
  <summary>Reliability</summary>
  
Reliability is a fundamental quality of good software. Without it, technology loses its value and purpose. Reliability is not limited to large systems; it applies to every line of code. Reliable code is defined by the following qualities:

1. **Correct**: The code performs its intended function accurately.
2. **Stable**: It consistently behaves as expected under various conditions.
3. **Resilient**: It gracefully handles errors and unexpected situations.

</details>

<details>
  
  <summary>Correctness</summary>
  
Correct code meets predefined expectations and requirements. For instance, if you write a function to validate email addresses, it should accurately determine the validity of various email formats:

### Establishing Correctness

1. **Understand Requirements**:
   - Clearly define what constitutes a valid email address.
   - Requirements should guide how the code should behave. For instance:
     - The function should return a positive result for valid email addresses.
     - It should return a negative result for invalid ones.

2. **Handle Edge Cases**:
   - Recognize and manage special scenarios and edge cases. Some email formats might be valid according to standards but may need different rules based on the application's needs.

3. **Use Existing Libraries**:
   - Prefer using well-tested open-source libraries for common tasks like email validation to avoid the complexities of creating your own solution.

4. **Test Thoroughly**:
   - Develop comprehensive tests to ensure your code meets all requirements and handles various scenarios effectively.

### Key Points

- Understand the problem and user needs.
- Refine requirements to be explicit and clear

</details>

<details>
  <summary>Stability</summary>
  
-  Stability is crucial for ensuring that technology consistently performs well without unexpected failures. In code, stability means that the software behaves reliably across different conditions and inputs.
### Achieving Stability

1. **Understand All Conditions**:
   - Ensure your code can handle various valid inputs and scenarios. For instance, a web application should function correctly across different screen sizes and environments.

2. **Account for Variability**:
   - Design code that is robust to changes and diverse conditions. Avoid dependencies on specific circumstances that may not always be present.

3. **Test Extensively**:
   - Use comprehensive testing to simulate a range of conditions and inputs. This helps ensure your code remains stable and performs correctly in varied situations.

### Key Points

- Stability ensures consistent performance and reliability.
- Understand and cater to all possible conditions and inputs.
- Test your code under different scenarios to verify stability.

By following these practices, you can enhance the stability of your code and build software that users can depend on.

</details>
