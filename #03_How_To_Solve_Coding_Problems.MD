<h1 align="center">How To solve coding problems</h1>

### Section overview
* **[Coding problems Cheat Sheet PDF](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/cheatsheet.pdf)**
* **[What Are Companies Looking For?](#look-for)**
* **[What We Need For Coding Interviews](#what-we-need-for-coding-interviews)**

* **[Exercise: Coding Interview - Thought Steps](#coding-q)**

* **[Section Summary](#section-summary)**

### <a name="look-for">What Are Companies Looking For?</a>

- **Analytic Skills**: How can you think through problems and analyze things?
- **Coding Skills**: Do you code well, by writing clean, simple, organized, readable code?
- **Technical knowledge**: Do you know the fundamentals of the job you're applying for?
- **Communication skills**: Does your personality match the companies’ culture?

### What We Need For Coding Interviews

![RoadMap](https://github.com/tsokac2/-_-_Data_Structures_Algorithms/blob/main/src/02.JPG)

**[Back to The TOP](#section-overview)**
#

### <a name="coding-q"> Exercise: Coding Interview - Thought Steps</a>

#### Challenge
Given 2 arrays, create a function that lets a user know (true/false) whether these two arrays contain any common items.

#### Step By Step through a problem

#### 1. When the interviewer says the question, write down the key points at the top (i.e., sorted array).
    - Make sure you have all the details.
    - Show how organized you are.

For Example:
- ``const array1 = ['a', 'b', 'c', 'x'];``
- ``const array2 = ['z', 'y', 'i'];``

**Should return**: ``false`` -  because there is nothing common between these 2 arrays.

- ``const array1 = ['a', 'b', 'c', 'x'];``
- ``const array2 = ['z', 'y', 'x'];``

**Should return**: ``true`` - because the item `'x'` is present in `array1` and `array2`.

#### 2. Make sure you double-check:
    - What are the inputs?
    - What are the outputs?

In this case, we have:
- 2 input parameters are always `arrays`.
- As a result, we always want to return `true` or `false`.

**NOTE**: This is a very important step; don't jump into the coding right away!

#### 3. What is the most important value of the problem?
- Do you have time, space, and memory, etc.?
- What is the main goal?

You can ask, "How large the array is going to be." If it's a constant array, we don't have to worry about Time Complexity, Space Complexity, and Big O.
- Is Time Complexity more important?
- Is Space Complexity more important?

#### 4. Don't be annoying and ask too many questions.

#### 5. Start with the naive/brute force(easy solution) approach. The easiest way to solve the problem!
- The first thing that comes to mind.
- It shows that you're able to think well and critically (you don't need to write this code, just speak about it).

**Easy solution**:
So immediately this looks like we're comparing two different arrays and we're going to have two ``for`` loops, one nested on top of each other.

And right away we know that that's a Big O:``O(n^2)``.

The important thing is that you let the interviewer know that this is the brute force or the easy.

**Easy/Brute solution:**
```
const array1 = ['a', 'b', 'c', 'x'];
const array2 = ['z', 'y', 'i'];

const containsCommonItems = (arr1, arr2) => {
    for(let i = 0; i < arr1.length; i++){
        for(let j = 0; j < arr2.length; j++){
            if(arr1[i] === arr2[j]){
                return true;
            }
        }
    }
    return false;
}

containsCommonItems(array1, array2);
```
The Big O is: ``` O(a*b)``` - how can we make this faster?

We know that:
- Iterating through half a collection is still ``O(n)``
- Two separate collections: ``O(a*b)``

#### 6. Tell them why this approach is not the best?
- Two nested ``for`` loops - try to avoid these solutions.
- ``O(n^2)`` or higher.
- Code is not readable.

#### 7. Walk through your approach, comment things and see where you may be able to break things.
- Any repetition, bottlencks like ``O(n^2)``, or unnecessary work?
- Did you use all the information the interviewer gave you?
- Bottleneck is the part of the code with the biggest Big O. **Focus on that**.
- You might not see a solution right away, and that is because you need to practice a few of these problems to understand a common pattern.

**Let's try different solution** - to improve a Time Complexity and change the Big O:
Most common patern in coding interviews:
- Create a new object for the first ``array1`` to store all the array items.

#### 8. Before you start coding, walk through your code and write down the steps you are going to follow.

```
function containsCommonItem2(arr1, arr2) {

  // 1 - loop through first array and create object where properties === items in the array

  // 2 - loop through second array and check if item in second array exists on created object. 
}
```

**Half-way Summary of the excercise:**

- Although we haven't given a clear solution, we've been talking about how we solve the problem.
- The interviewer sees how we think, sees what steps we take
- Sees that we're making smart, critical decisions to go from understanding the problem to solving the problem in a naive way
- Understanding why this might not be the best way, and then start to think about possible solutions.
- And the beauty of this approach is that no matter whether we get this part correct, maybe our assumptions are wrong and we can't do this.
- We're showing the interviewer that we're thinking through a problem and we're making small, logical steps towards a solution.
- And this is a lot better than just coding right away, trying a solution and see if you get it right or wrong.
- An interviewer is going to have a good understanding of your abilities and your thought process this way, and these are the type of people that they want to hire.

#### 9. Modularize your code from the very beginning.
- Break up your code into beautiful small pieces and add just comments if you need to.


#### 10. Start actually writing your code now
- Keep in mind that the more you prepare and understand what you need to code, the better the whiteboard will go.
- So never start a whiteboard interview not being sure of how things are going to work out.
- That is a recipe for disaster.
- Keep in mind:
    - A lot of interviews ask questions that you wan't be able to fully answer on time.
- So think:
    - What can I show in order to show that I can do this and I am better that other coders.
- Break things up in Functions(if you can't remember a method, just make up a function and you will at least have it there.)
- Write something, and start with the easy part.

#### 11. 


**[Back to The TOP](#section-overview)**
#
### Section Summary

Solving coding problems is a fundamental skill for any programmer. It requires a combination of problem-solving, critical thinking, and creativity. Here's a step-by-step guide on how to approach coding problems:

#### Understand the problem statement:
- Read the problem carefully and make sure you fully comprehend the requirements.
- Identify the input and output of the problem.
- Break down the problem into smaller, manageable tasks.
- Try to visualize the expected solution.

#### Choose the right data structure and algorithm:
- Analyze the problem and determine the most appropriate data structure to store and organize the data.
- Select the most suitable algorithm to solve the problem efficiently.
- Consider the time and space complexity of different algorithms to choose the most performant one.

#### Write pseudocode:
- Before diving into actual code, express the solution in pseudocode, which is a high-level, English-like description of the algorithm.
- Pseudocode helps you clarify your thoughts, identify potential issues, and avoid coding errors.
- It also serves as a reference point for translating the algorithm into the chosen programming language.

#### Implement the solution:
- Start coding the solution in your chosen programming language.
- Use clear and concise code that is easy to understand and maintain.
- Break down complex tasks into smaller, manageable functions.
- Document your code with comments to explain the purpose of each section.

#### Test your solution:
- Write test cases to thoroughly validate the correctness of your solution.
- Test the code with various input values, including edge cases and boundary conditions.
- Use automated testing frameworks to automate the testing process.
- Analyze the test results to identify and fix any errors or bugs.

#### Optimize and refactor:
- Once the code is working correctly, analyze its performance and identify areas for improvement.
- Optimize the algorithm to reduce its time and space complexity.
- Refactor the code to improve its readability, maintainability, and code quality.

#### Seek help and resources:
- Don't hesitate to ask for help from experienced programmers or online communities if you get stuck.
- Utilize online resources, such as documentation, tutorials, and code repositories, to learn from others.
- Practice regularly and solve a variety of problems to improve your problem-solving skills.

Remember, problem-solving is a skill that develops over time with practice and experience. Don't be discouraged if you encounter challenges along the way. Keep learning, practicing, and refining your approach, and you'll become a more proficient problem solver and programmer.

**[Back to The TOP](#section-overview)**
#