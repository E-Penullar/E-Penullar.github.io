---
layout: essay
type: essay
title: "A How-to and How-not-to Guide on Asking Smart Questions"
# All dates must be YYYY-MM-DD format!
date: 2026-06-08
published: true
labels:
  - Questions
  - Stack Overflow
---

<img width="200px" class="rounded float-start pe-4" src="../img/art/E11_thinking.png" alt="Thinking really hard about this...">

No single person can know everything, and in an age of programming and industry of software development, it's important to be able to communicate with fellow programmers. To ask questions, whether as an amateur or as a professional, is part of the experience of becoming a better developer. For novices, it gives them the opportunity to learn from those more proficient. And for experts, collaboration is key to tackling difficult problems, as a diverse array of perspectives may help when one is feeling lost in their own head. 

As such, it's important to be able to ask good question — questions that are direct and concise, that get the point across. Questions that can be easily understood can be better answered. In Eric Steven Raymond's article on *[How To Ask Questions The Smart Way](http://www.catb.org/esr/faqs/smart-questions.html)*, he describes good questions to be specific, and written in clear and grammatically-correct language. When formatting your "smart" question, it would explicitly describe the issue and the desired goal, including informative symptoms of the problem and meaningful queries. It's also important that your questions comes across as polite, and simplify any code you post, as it will encourage useful answers. Conversely, a "not so smart" questions would be behave as an antithesis; meaningless subject headers, hard to understand or read, vague and arrogant questions all lead to either bad answers or none at all. 

To better demonstrate the difference between the, I included two Stack Overflow posts as examples of what a smart question and what a not so smart question might look like.


## An Example of a Smart Question

This question is titled "[How to add images to README.md on GitHub?](https://stackoverflow.com/questions/14494747/how-to-add-images-to-readme-md-on-github)", and it satisfies many of Raymond's criteria for a smart question. 

Here it is shown below:

<img width="600px" src="../img/code/E11_Smart.png" alt="An Example of a Smart Question: OP asks how to include images in a README File, and had tried searching online. Simple, to-the-point, and written in clear language; there are many replies from other people." class="rounded mx-auto pe-4">

There's plenty of context given to understand the situation and how to better help: we're told that OP is new to Github and is trying to include some images in a README File, and we also know that they've tried looking up the solution but came up empty. It's a very short and simple question, but they got their point across and because of that, they've gotten plenty of responses of people giving their input. 

## An Example of a Not so Smart Question

On the other hand, we have a question titled "[Getting error while running node app. Please help me solve this error](https://stackoverflow.com/questions/67514403/getting-error-while-running-node-app-please-help-me-solve-this-error)". First off, the header is terribly vague and crude. It demands help and we don't even know what exactly the problem is yet! And when you see the post, we're told that OP couldn't run their code and tried everything, but they failed to include what exactly they tried. They also provide several files of code, but omit what the goal of getting it to run. 

For example:

```
// Source - https://stackoverflow.com/q/67514403
// Posted by Khetesh Singh
// Retrieved 2026-06-08, License - CC BY-SA 4.0

const fs = require("fs");
const path = require("path");

const p = path.join(
    path.dirname(process.mainModule.fileName),
    "data",
    "cart.json"
);

module.exports = class cart {
    static addProduct(id, productPrice) {
        //Fetch the previous cart
        fs.readFile(p, (err, fileContent) => {
            let cart = { products: [], totalPrice: 0 };
            if (!err) {
                cart = JSON.parse(fileContent);
            }
            //Analyse the cart => Find existing product
            const existingProductIndex = cart.products.findIndex(
                (prod) => prod.id === id
            );
            const existingProduct = cart.products[existingProductIndex];
            let updatedProduct;

            // Add new product/ increase quantity
            if (existingProduct) {
                updatedProduct = {...existingProduct };
                updatedProduct.qty = updatedProduct.qty + 1;
                cart.products = [...cart.products];
                cart.products[existingProductIndex] = updatedProduct;
            } else {
                updatedProduct = { id: id, qty: 1 };
                cart.products = [...cart.products, updatedProduct];
            }
            cart.totalPrice = cart.totalPrice + +productPrice;
            fs.writeFile(p, JSON.stringify(cart), (err) => {
                console.log(err);
            });
        });
    }
};
```

This huge chunk of code might describe what they're doing — the code itself includes comments, and there's a huge block of what their output looks like after running their code — but it's all a bunch of noise. There could a whole slew of solutions that may or may not have anything to do with the code in question, or it could be this person's software, we don't know because OP did not include such info. 

Raymond' suggests to not ask open-ended questions, that people would be more likely to give useful responses if you give explicit questions as to what you want from other, where that be pointers or outright solutions. Yet all OP says is "any help will be great." This combined with the lengthy blocks of code, makes for huge ask from — people would much rather spend their time elsewhere than deal with huge volumes of code and open-ended time sinks. There's so much information yet very little context, and as a result this question has no responses nor follow-ups, despite being written 5 years ago. 

## So What's the Takeaway

It can be frustrating whenever you hit a roadblock when programming, and even more so when you don't know how or why. Asking questions can alleviate that agitation, but it's important to be able to ask questions that can actually be answered. I've found myself wanted to ask questions too, but I was too worried about asking "dumb questions" or being to stupid to ask. Both of which were inane concerns: for one, there's no such thing as "dumb questions" because something that might be obvious to you may seem new to someone else. And for another, it's foolish to think you're too stupid to understand because why else would you be asking questions in the first place if you didn't want to learn? But I digress, the point is — with what I know now about asking smart questions — I can see myself asking more questions in the future, and communicating better in my community when doing so.

