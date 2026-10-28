+++
date = '2025-06-27T12:00:31Z'
draft = false
title = "Data management tips for educators"
+++

I gave a presentation at yesterday’s [2025 Metropolitan Educational Research Consortium (MERC) Summit](https://www.eventcreate.com/e/2025-merc-summit) titled “Data Management Tips for Educators.” The [slides are available here](https://docs.google.com/presentation/d/1_quXVdA_3GWvIkXUHWX5XqG-NBWojpxQq83AZSlZGTc/edit?usp=sharing) if you’re interested.

------------------------------------------------------------------------

The gist of my talk is that we, as educators, often have lots of data available to us, whether that’s through reports from digital learning platforms, student information system extracts, state reporting, or something else. And we’re being increasingly asked to “use data to make decisions.” But the vast majority of people in schools and school division central offices who are tasked with managing data – aside from the small handful of folks who work on the Database Services or Research teams – don’t have any formal training in data management. My experience is that data management tasks are thrust upon whichever poor soul has some sliver of bandwidth, is the subject matter expert, naively volunteers to help, or is “good with spreadsheets,” and this seems to be especially true in schools. Regardless, the people who end up responsible for “managing their schools’ data” are almost invariably learning as they go.

In some ways, managing data is like going to the gym. Imagine being dropped into a sprawling mega-gym and someone saying to you “you have access to all of this equipment. Go work out!” If you’re not a regular gym-goer, this is probably overwhelming! Even if you are a person who spends a lot of time at the gym, it can still take some time to get your bearings, especially if this gym is different from your usual gym.

Although it’s obviously not possible to condense all of the nuance that goes into effective data management into a 15 minute talk, I tried to come up with 3 tips that people can apply and notice immediate improvements. These are:

1.  Align data structures to questions you want to answer
2.  Develop standards and conventions
3.  Leverage “database-style” thinking for managing large data sets

I’ve written about [aligning data structures to questions](/edudata/does-your-datas-structure-match-the-question-you-want-to-answer/) and developing standards and conventions ([read: documentation](/edudata/do-less-document-more/)) before on this blog.

To continue with the gym analogies, these roughly translate to:

1.  Choosing the right workout plan for your goals
2.  Adopting consistent routines and proper form
3.  Organizing the gym effectively

Regarding the first point – if your goal is to run a PR in the marathon, your training is going to look very different than if your goal is to compete in a bodybuilding show. You need to determine your goal ahead of time, then develop a workout plan that will help you meet that goal. If you just start randomly lifting weights here, running there, maybe doing a bit of yoga whenever the mood strikes, it’s not like you can just decide to run a marathon after 6 months of undirected training and be prepared for it. Likewise, when you’re managing data, you need to start with the question you’re trying to answer and then make sure the structure of your data allows you to answer that question. And you have to start with an actual question – a general topic isn’t sufficient. Consider the following questions:

- Which students are on track to be chronically absent?
- Is our attendance intervention addressing absenteeism in our students?

Both relate to attendance, but they require different data to answer. The first question can be answered by just looking at the number of absences for each of your students. Data in this format won’t be able to answer the second question, though, because what you really need is the number of absences (and enrollment days) before the intervention as well as the number of absences (and enrollment days) after the intervention. Ideally, you’d want daily attendance records for all students as well as the day on which each eligible student began the attendance intervention.

Regarding the second point. If I decide I want to get stronger, larger legs, I might decide to back squat. Fortunately for me, people have been back squatting for a long time, and lots of smart powerlifters and exercise scientists have developed movement standards that describe the safest, most effective ways to squat. If I consistently follow these standards, I can be pretty confident that I’m going to be successful in getting bigger, stronger legs.

Another benefit is that I’m better able to track my progress over time. If I’m performing the squat the same each time, I can attribute changes in the amount of weight I’m lifting to changes in strength rather than variations in form. Adopting consistent routines with proper form will also help me share my workout plan with others.

Basically, this comes back to documenting all of your shit. You should document more than you think you need to, because future-you will not remember everything that current-you knows, even if current-you thinks it’s so obvious that variable Z is the product of X and Y in cases where variable A is missing. Document everything.

Finally, regarding the 3rd point. Imagine how confusing the gym would be if equipment were just randomly strewn throughout the building. If a random treadmill was dropped right next to the olympic lifting platforms, and another was inside the yoga studio, and if there were a pair of 50 lb dumbbells on the kettlebell rack.

I often see people try to make “master data sheets” that serve as “one stop shops” for student demographic, attendance, grade, discipline, and test score data, among others. This is the equivalent of going to the gym and having the equipment completely disorganized. Master data sheets are inefficient – both to read and maintain – and they’re just begging for someone to accidentally fat-finger something and ruin the whole sheet. 

I’d also argue that there are very few cases where I need to see attendance, grade, discipline, and test data for multiple students all at the same time.

A better approach is to adopt a relational database model, where data is kept in smaller, self-contained tables pertaining to a single entity (e.g. attendance). Data in each table can be connected to data in other tables using keys (e.g. we can match attendance data to grades data as long as both tables contain student IDs). This makes the data easier to update, allows us to adopt different structures for each table, and is more natural for exploring data on a given topic. If I want to look at attendance information, I just look at the attendance table; I don’t have to slog through students’ 1st quarter ELA grades and their 3rd grade math test scores just to see how many absences they have.

So, to wrap up:

1.  Make sure your data helps you answer your actual questions;
2.  Document everything;
3.  Create multiple small, linkable tables instead of one “master datasheet”

There’s obviously more to data management than this, but this isn’t a bad start. If you’re interested in reading more, I strongly recommend reading Crystal Lewis’s [*Data Management in Large-Scale Education Research*](https://datamgmtinedresearch.com/).
