<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://user-images.githubusercontent.com/25423296/163456776-7f95b81a-f1ed-45f7-b7ab-8fa810d529fa.png">
  <source media="(prefers-color-scheme: light)" srcset="https://user-images.githubusercontent.com/25423296/163456779-a8556205-d0a5-45e2-ac17-42d089e3c3f8.png">
  <img alt="Shows an illustrated sun in light mode and a moon with stars in dark mode." src="https://user-images.githubusercontent.com/25423296/163456779-a8556205-d0a5-45e2-ac17-42d089e3c3f8.png">
</picture>

# Clean-Code-Notes
This repository contains a concise summary of the book "Clean Code in JavaScript" by James Padolsey. It compiles the core ideas, key points, and essential principles from each chapter of the book. The summary is intended to provide a quick reference to the most important concepts without the need to reread the entire book.

# Table of Contents

## Preface 1

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

  A model or conceptual model is a schematic or representation that describes how something works. We create and adapt models all the time without realizing it. Over time, as you gain more information about a problem domain, your model will improve to better match reality.
  
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

  The first point of failure is typically misunderstanding the problem. If we don't understand what users are truly trying to accomplish, and we have not received all requirements, then we will inevitably retain a bad model of the problem and thus end up implementing the wrong solutions.

  **Example:** Imagine that this scenario occurs at some point before the invention of the kettle:

  *Susanne (engineer):* Matt, we've been asked to design a vessel that users can boil water with.

  *Matthew (engineer):* Understood; I will create a vessel that does exactly that.
  
  Matthew asks no questions and immediately gets to work. One day later, he comes up with a contraption without a handle, which he later adds after receiving feedback. This miscommunication could have been avoided by better understanding the user's needs from the beginning.

</details>

<details>
  <summary>Writing Code for Humans</summary>

  This entire book is concerned with teaching you how to write clean code in JavaScript. Writing code for humans is broadly about the clarity of intent, while writing code for machines is broadly about functionality. These needs cross over, but it's vital to discern the difference.

  **Example:** Compare the following two pieces of code:

  ```javascript
  function chb(d,m,y) {
      return new Date(y,m-1,d)-new Date / 6e4 * 70;
  }
const AVG_HEART_RATE_PER_MILLISECOND = 70 / 60000;
function calculateHeartBeatsSinceBirth(birthDay, birthMonth, birthYear) {
    const birthMonthIndex = birthMonth - 1;
    const birthDate = new Date(birthYear, birthMonthIndex, birthDay);
    const currentDate = new Date();
    return (currentDate - birthDate) / AVG_HEART_RATE_PER_MILLISECOND;
}
The latter code is much clearer, communicates the programmer's intent, and is easier to understand and maintain.

</details>
