---
layout: essay
type: essay
title: "The Importance of Smart Questions in Software Engineering"
# All dates must be YYYY-MM-DD format!
date: 2024-09-12
published: true
labels:
  - Questions
  - Answers
  - StackOverflow
---

In the fast-paced field of software engineering, effective communication is crucial to evolving your skills as a developer. One key component to learning is the communication skills and the ability to ask smart questions that are clear, specific, and well researched. Eric Raymond’s essay, How to Ask Questions the Smart Way, outlines guidelines to interact effectively with open source communities. The guidelines emphasize preparation, clarity and consideration to ensure that you get the best responses to learn from. I will demonstrate why smart questions are important by analyzing two real-life examples from StackOverflow; one that follows the guidelines and one that does not, and how these illustrate the difference in outcomes when asking smart or “not smart” questions. 

## Thoughtful, Detailed, and Focused: UX and TypeScript Integration Issue

Eric Raymond’s essay, How to Ask Questions the Smart Way, provides a pretty solid blueprint for doing just that. It outlines the importance of being prepared, clear, and considerate when asking questions in technical communities, so that you can not only get the help you need, but also learn and grow from the experience. To demonstrate why this approach matters, I’ll take you through two real examples from StackOverflow: one that hits the mark with a smart question, and one that, well, doesn’t.

## Smart Question: Thoughtful, Detailed, and Focused

A strong example of a smart question on StackOverlfow is “Can you force a React component to rerender without calling setState?” This developer is working on a react project where they want an external observable object to listen for changes. Their question is well structured and provides details on the tools they are using, the problems they encounter, as well as a code example. 

They include a snippet of TypeScript showing how they are managing button focus and event handling but note that screen readers are not interpreting their custom components correctly. The developer then lists the exact screen reader software they’ve tested, describes what they expected to happen versus what is actually happening, and asks for guidance on how to refactor their code to meet the accessibility standards. 

This question demonstrates a clear understanding of the problem, includes necessary context, and shows that the user has already researched and attempted solutions. The answers provide thoughtful feedback, suggesting improvements to the code structure and recommending how to force rerenders and alteritives to force updates. 


**Q:** I have an external (to the component), observable object that I want to listen for changes on. When the object is updated it emits change events, and then I want to rerender the component when any change is detected.

With a top-level React.render this has been possible, but within a component it doesn't work (which makes some sense since the render method just returns an object).

```
export default class MyComponent extends React.Component {

  handleButtonClick() {
    this.render();
  }

  render() {
    return (
      <div>
        {Math.random()}
        <button onClick={this.handleButtonClick.bind(this)}>
          Click me
        </button>
      </div>
    )
  }
}
```
Clicking the button internally calls this.render(), but that's not what actually causes the rendering to happen (you can see this in action because the text created by {Math.random()} doesn't change). However, if I simply call this.setState() instead of this.render(), it works fine.

So I guess my question is: do React components need to have state in order to rerender? Is there a way to force the component to update on demand without changing the state?

## Smart Question Analysis

The developer clearly defines their problem, provides relevant context, and includes a code snippet to demonstrate their current approach. This level of detail allows respondents to immediately understand the issue, offer targeted solutions, and even expand on best practices for managing component rendering in React.

The question not only solves the immediate problem but invites broader discussion on React lifecycle management. Several answers offer updated techniques for rerendering using hooks, showing how even older questions can continue to serve the community as technology evolves. This engagement is a direct result of how thoughtfully the question was posed, leading to a wealth of valuable information.


**A:** In 2021 and 2022, this is the official, but also officially discouraged, way to forceUpdate a React Functional Component.
Like this:

```
 const [, forceUpdate] = useReducer(x => x + 1, 0);

  function handleClick() {
    forceUpdate();
  }
```

I know the OP is for a class component. But the question was asked in 2015 and now that hooks are available, many may search for forceUpdate in functional components. This little bit is for them.

Edit 18th Apr 2022

It's usually bad practice to force update your components.

A few reasons that can cause the need to use force updates.

- Not using state variables where you have to - local, redux, context.
- The field from the state object you are trying to access and expecting to update/change is too deeply nested in objects or arrays. Even Redux advises to maintain flat objects or arrays. If only one field value changes in a complex object, React may not figure out that the state object has changed, thus it does not update the component. Keep your state flat and simple.
- The key on your list items, as mentioned in another answer. In fact, this can cause other unexpected behaviors as well. I've seen lists where items are repeatedly rendered (duplicates) because the keys aren't identical or the keys are just missing altogether. Always request the backend team to send unique ids everywhere possible! Avoid using array indexes for keys. Do not try to create unique ids on the front-end by using nanoid, uuid or random. Because ids created using above methods change each time the component updates (keys provided to a list need to be static and the same on each render). Creating unique ids is usually a backend concern. Try your best to not bring that requirement to the front-end. The front-end's responsibility is only to paint what data the backend returns and not create data on the fly.
- If your useEffect, useCallback dependency arrays do not have the proper values set. Use ESLint to help you with this one! Also, this is one of the biggest causes for memory leaks in React. Clean up your state and event listeners in the return callback to avoid memory leaks. Because such memory leaks are awfully difficult to debug.
- Always keep an eye on the console. It's your best friend at work. Solving warning and errors that show up in the console can fix a whole lot of nasty things - bugs and issues that you aren't even aware off.
A few things I can remember that I did wrong. In case it helps..


## Not-So-Smart Question: Vague and Unclear

On the other hand, a not-so-smart question is [“Is passing an encrypted idToken in a JSON body a security issue?”](https://stackoverflow.com/questions/78979185/is-passing-an-encrypted-idtoken-in-a-json-body-a-security-issue) This question is vague and doesnt provide specific details. 

The developer mentions they’re working on setting up sessions in cookies to authenticate a user and that they have been encountering issues. The developer doesnt say what third party cookies they are working with and potential methods. They don’t explain what exactly is going wrong or what steps they’ve already taken to try and fix it. There are no code snippets and the question is too vague to provide any helpful answers. 

Unsurprisingly, negative votes on the question reflect the lack of information. It demonstrates how a lack of clarity and specificity can lead to poor engagement. The question is vague, with little context provided about the encryption method, API, or even the broader authentication setup. It leaves too many unanswered questions, making it difficult for others to offer meaningful help. As a result, the question is closed entirely, illustrating how an unclear inquiry can waste both the asker’s and the community’s time.


**Q:** I have been working on setting up session cookies to help authenticate a user. We have been hitting some snags with third party cookies and now a new dev thinks we should change our auth method. He thinks the best method for us to send over an encrypted idToken in the JSON body for our API requests.

Is this a secure method to authenticate users?

## Conclusion

In the field of software engineering, especially in complex areas like React development or security, the quality of the questions we ask directly impacts the quality of the answers we receive. Smart questions—those that are clear, specific, and show effort—are far more likely to result in helpful, detailed responses. They not only solve immediate issues but also foster productive discussion and learning opportunities for both the asker and the wider community.

Vague questions with little context or effort often lead to dead ends. Without enough information to work with, even the most knowledgeable members of the community will struggle to provide meaningful assistance. In the end, smart questions benefit everyone involved by promoting efficient, effective problem-solving and a positive collaborative environment. Asking the right question is the first step toward finding the right solution.
