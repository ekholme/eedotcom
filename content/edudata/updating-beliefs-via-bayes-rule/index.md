+++
date = '2025-01-10T13:00:31Z'
draft = false
title = 'Updating beliefs via Bayes’ Rule'
+++

We talk a lot in education about “using data,” and my general take is that the phrase “using data” doesn’t actually mean anything. But, if we want to be gracious and ignore all of the vagaries that come along with that phrase, then I think that “applying [Bayes’ Rule](https://en.wikipedia.org/wiki/Bayes%27_theorem)” is what most people mean when they talk about “using data.” 

Bayes' Rule mathematically formalizes a process for updating beliefs that incorporates both prior beliefs and new data. It can be used to estimate lots of things, but we’ll limit this to beliefs here for the sake of concision. If you’re interested in learning more, the book [Bayes Rules!](https://www.bayesrulesbook.com/) by Johnson, Ott, and Dogucu is awesome, and the first chapter is very accessible (subsequent chapters assume some knowledge of programming and mathematical notation).

*Disclaimer – this post isn’t trying to be mathematically rigorous. The goal is to present the spirit of Bayesian stats broadly, and this requires some imprecise and hand-wavey language. If that bothers you, I’m sorry.*

The premise of Bayes’ Rule is that we have some prior belief about a thing, and when we encounter new data about that thing, we combine the new data with the prior belief to arrive at a new belief. That new belief will then, in turn, function as the prior belief when we encounter yet more new data, and we combine that prior belief with data yet again update our belief, ad infinitum.

Implicit in this framing is that our prior beliefs can be weak, strong, or anywhere in between, and any new data we encounter can likewise be weak, strong, or anywhere in between.

An obvious (to me) application of this in education is teachers’ beliefs about students’ academic ability. For the sake of an example, let’s say that I’m an 8th grade English/Language Arts teacher, and that students’ reading proficiency can rigorously be quantified as falling between 1 and 100, where higher scores are better. Please just go with it – I recognize all of the objections we could make about this.

At the beginning of the school year, before a single student steps a single Croc-wearing foot inside my classroom, I might reasonably assume that all of my students are average readers – that they’d score a 50 on this 1-100 scale. But this would be a pretty weak prior belief. I’m assuming these students are average simply because I have no other data to base my belief on, and absent any other data, the average is the most reasonable guess.

But then all of the students come in, wearing all different kinds of Crocs, and I give them their first homework assignment, in which they have to read and respond to a short nonfiction passage. When I review the responses to this assignment, I use this new data to update my beliefs about my students. Jayden’s response is thorough and well-thought out. Dan *technically* turned something in, but it’s not good. Joy didn’t turn anything in. Although this is a single homework assignment, and although a response on a homework assignment may not be a great indicator of actual ability, it does give me *some* data. So I might tweak my beliefs about Jayden and Dan – maybe now I think Jayden is more like a 55 and Dan is a 48. I wouldn’t change my beliefs about Joy since I have no new data about her. So now I have updated beliefs, but they’re still not strong beliefs because they're based on a single, not-terribly-great piece of data.

Then, we take a beginning-of-the-year benchmark test that’s mandated by the state. Jayden does well, Joy absolutely crushes it, Dan does better than average. And since the state test has (in theory!) been created and rigorously validated by some testing company like Pearson or ETS, I probably put more emphasis on this test when I update my beliefs than I put on the homework assignment. So now on our scale of 1-100, maybe Joy is at like an 85, Jayden is at a 70, and Dan is at a 55. These numbers are purely made up, but you get the point.

And then this process continues. Each time I grade a paper, discuss a book, watch a student annotate their reading, whatever, I update my beliefs about that student’s reading proficiency. Maybe I become more certain as I collect evidence that confirms your beliefs. Maybe I become less certain as I collect evidence that challenges my beliefs. Maybe (hopefully!) a student is becoming a better reader over the year and I need to update my beliefs accordingly.

This is Bayesian updating. 

Of course, this isn’t only useful for framing student reading proficiency. A school principal might use the same Bayesian knowledge-building process when thinking about how effective a school-wide behavior intervention is. And a school district administrator might use the same process when thinking about the effectiveness of a teacher-retention policy. Hopefully at the district level there’s more formal evaluation and actual statistics rather than the process being purely vibes-based, but even with real math, the process is still basically the same.

This isn’t anything groundbreaking. Bayes’ Rule has been around for literal centuries. The process is also obvious and common-sensical. When I’ve talked about this with folks I work with, their response is basically “duh.” But I *do* think having this framework as a way to think about “using data” can be helpful because it gives us some way to latch onto a frustratingly slippery concept.
