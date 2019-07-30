---
layout: post
author: Sébastien Varlet
title: "Servant framework, or framework servant?"
date: "2019-07-29 14:00:00 +0100"
comments: true
categories: [Architecture]
tags: [frameworks, SOLID, dependency, elixir, phoenix, ecto, clean architecture]
---

Robert C. Martin published the “Clean Architecture: A Craftsman’s Guide for Software Structure and Design” book. It describes principles to design maintainable software, that is software that we can easily change for new business requirements. Many topics are covered by the author: functional programming, the SOLID principles, layers, components, boundaries, frameworks, etc.

I’m an architecture nerd. I develop my architecture tool belt to guide myself when designing solutions to business problems. I seek designs which reduce rigidity and complexity so I can hi-five myself later. I used to wonder how to solve problem X _with framework Y_. The problems became increasingly specific to my domain and finding solutions _for framework Y_ made my life harder. There is only so much a framework can do for your business.

Robert C. Martin makes a valid point:

> [...] regardless of their high-minded motives, those [framework] authors do not have your best interest at heart. They can’t, because they don’t know you, and they don’t know your problems.

 Like any product, frameworks only solve a subset of your problems. Let’s make sure they don’t create more!

## Frameworks are not free

Are you now struggling to write maintainable software? Are you nostalgic of your application’s infancy? Some will say it’s a cheeky comparison. I don’t think so.

When you solve a problem, do you solve problem X _with framework Y_? No? will your google search history confirm?

If the delivery of value to your customers depends on your ability to make a framework do it, then your framework is not a multiplier of your talent. It’s a divisor. Perhaps it is time to reconsider the place of the framework in your architecture.

## Break your chains!

Programming took a good turn for me when I stopped worrying about mastering a framework and learnt timeless design principles.

I also used to solve problem X _with framework Y_. Experience taught me that frameworks are not built for my business domain. This is the space in which my company develops its know-how, make products and sell them. Eventually, I learned that frameworks are not ways of life. I appreciate how they can help me but I also appreciate their cost. Frameworks are not free. When I introduce a framework in my project, I make an investment. If it dictates how to solve my problems, eventually it becomes the problem. I stopped seeing them as a rigid architecture, or a required element of the architecture. Frameworks are just a tool, with pros and cons.

Describe your application. Is it a React+Redux application with middleware X, Y, Z? Is it a Phoenix/Ecto/LiveView application?

Or is it an elixir conference planner? An online shop selling vegan beauty products? Or real time fleet tracking?

When my mindset is aligned with a business, I don’t think anymore in terms of Phoenix, Ecto, Postgres, HTML, Channels, Rest, etc. They matter but, at the same time, they are irrelevant.

Learning these principles of Clean Architecture will show you how to design software focused on your business where frameworks are plugins.

Not the other way around.

## For functional programs too!

I learnt the meaning and implications of the SOLID principles when I was using Object Oriented Programming languages. These principles have guided me for half a decade as I developed frontend applications, backend applications and scripts in Ruby, Actionscript or Java.

Today, I develop software with Elixir and React. I believe the SOLID principles also apply when developing with a functional programming language. After all, unlike the Gang of Four design patterns, the SOLID principles do not impose a specific view on the solution. They do not require building blocks only present in Object Oriented Programming languages.

I feel that this opinion does not resonate much in the Elixir community. There are of course people who swiftly remind you to not think like an OO programmer. In my experience, it’s not explained by general disagreement. My intuition is it’s not valued as much as mastering some frameworks. Why is there a a lack of interest? Or is it already general tacit knowledge? I’m skeptical.

To be fair to the elixir community, I observed this well before departing for Functional City. That suggests the issue is global. Yet I feel this is perhaps exacerbated in Functional City. Some functional programming enthusiasts wrongly associates these principles with OOP languages.

## Unlearn, Learn, Relearn

As one starts to learn elixir, they will repeatedly hear they must “unlearn everything” so they don’t try to structure their programs with the usual suspects of OO languages: classes, objects, constructors, inheritance, etc. I think it’s a good piece of advice. It helped me too. But how much should we unlearn?

Some techniques and patterns reduce complexity and are paradigm agnostic: abstraction, polymorphism, dependency inversion, etc. Disagree? Have you heard about Haskell Typeclasses? Clojure protocols?

Posts on these topics on the Elixir forum don’t look as popular than posts related to Phoenix or Ecto. I don’t have the stats though, do you?

[Phoenix is not your application](https://youtu.be/lDKCSheBc-8). Let’s add that Ecto is not your application either. So why do we focus so much on the delivery and the storage of bits and not as much on our domains? Why don’t we assemble both with dependencies going in the right direction?

## The things I now do

Frameworks are great. Despite their learning curve, they save my time. I use them all the time. I am grateful to all their authors and contributors.

However, I keep frameworks at a distance so they remain *a* tool, one that I could easily replace by something more convenient, faster or simpler.

When I write some persistence logic, it fulfills a contract defined by the business rule. It talks the language of the business rule. It gets data shaped by the business rule. It returns data in the shape defined by the business rule. If I let Ecto Changesets penetrate the business layer, the business rule serves Ecto and the relational database. I don’t want that.

When I write a controller, it delegates the work to the business rule. It triggers the business rule with data which shape is defined by the business rule. The business rule return data shaped for its own convenience. If I let a Conn struct penetrate the business layer, the business rule serves Phoenix and the web. I don’t want that.

My business layer remains agnostic of the tools which supports my work. The business layer is never chained to choices of yesterday. Today, I’m using Ecto. Tomorrow, I can replace it. Perhaps a full-fledged Phoenix application is more than I needed. Let’s replace it with the Raxx toolkit!

My code is simple and I can pivot as my domain knowledge improves.
