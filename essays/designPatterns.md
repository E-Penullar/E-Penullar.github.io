---
layout: essay
type: essay
title: "Remaking the Wheel must be Exhausting"
# All dates must be YYYY-MM-DD format!
date: 2026-07-30
published: false
labels:
  - Design Patterns
  - Final Project
---

I think I've had enough of this bumpy ride. The ride being software engineering, because I hadn't realized there was still so much more I had to learn. Especially with this Final Project I've been working on currently — can't say I pity web developers much though. And to think there would be such a thing for the kinds of code you can use again and again for efficiency, and that it would have a name.

<hr>

## Reduce, Reuse, and Recycle





<hr>

## Developing the Catalog

For the Final Project of this course, I found myself joining a group in developing a centralized roster of UH Manoa Clubs — a web application that held the information on campus clubs, and gave these resources for students or club officers to view and edit. Personally, I worked on implementing the Playwright tests for the application, and ensuring the pages and forms ran smoothly. Playwright being a tool for web automation, used to run tests and simulate user actions to ensure a web application functionals alright. An example of a few design patterns within my code are Fallback / Default Value Design Patterns and Factory Patters, which are Behavioral and Creational types of design patters respectively.

A Fallback / Default Value Design Pattern is a pattern or method that offers an alternative response or safe substitute value, usually when a primary value or input is missing, empty, or fails. In this case, the following line provides alternative URLs, first starting with baseURL, then VERCEL_URL, then 'http://localhost:3000':

```html

baseURL: process.env.BASE_URL || (process.env.VERCEL_URL ? `https://${process.env.VERCEL_URL}` : 'http://localhost:3000')

```

There also this Factory Pattern, which is used for object creation, and hides complex instantiation logic behind a single function or method. In this case, Playwright provides a single function that takes various configuration properties to control how your tests run while also hiding all that complex code behind a simple line:

```html

export default defineConfig({ ... })
```

<hr>

## So, What Now?

Overall, I didn't put much stock on Design Patterns before this course, or even before this week when I learned about it. But it does seem like a very useful and important aspect for web development or even software engineering as a whole, if because of it's reliability in the industry. If anything else, I found this overview on [Design Patterns](https://ercin.medium.com/design-patterns-overview-3075789b961d) to be a practical read in helping me understand the concept.
