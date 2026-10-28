+++
date = '2026-03-13T12:00:02Z'
draft = false
title = "Embracing a Unix-like philosophy toward data"
+++

*After quite a long hiatus, we’re back! My goal is to write more regularly, but, you know, we’ll see.*

When I was younger, I used to regularly watch Alton Brown’s *Good Eats* with my family. And, as any devotee of *Good Eats* remembers, Alton absolutely despised single-purpose kitchen gadgets – quesadilla makers, avocado slicers, hot dog toasters. All sorts of over-specialized slicers and pans and cookers and other devices. According to Alton, the true heroes of the kitchen were the multi-taskers – cast iron pans, sharp knives, thick bottomed saucepans, wooden spoons, forks. With a very few exceptions, kitchen tools that couldn’t be used for several tasks were wastes of both space and money.

I buy this logic when we apply it to the kitchen. An actual, physical location with a finite amount of space. I think it falls apart when we apply it to software, though, and particularly data tools. The multi-tasker data tool is the all-purpose dashboard. The one that shows – in our world of education – metrics relating to attendance, grades, discipline, performance on various tests, usage of learning apps, etc., all rolled up into a single screen. A single source of truth. A single place where we can go and have all of our questions answered. I’m sure you can picture what I’m talking about.

I have several issues with these types of dashboards, but the one I’m going to focus on today is clutter. These dashboards are *busy*. Too busy. And because they’re busy, they elicit a sort of psychological clutter. They shove all of these metrics and data points and trend lines into our limited monkey brains and make us feel as though we ought to address all of them. Right now! All at once!

But trying to do too many things at once is a great way to do nothing productive. Better to focus on a (very) few of your highest-priorities and worry about everything else later. This isn’t to say that if (for example) we want to prioritize improving attendance, we should neglect everything else, but rather that we shouldn’t delude ourselves into believing we can prioritize everything.

A better way to approach data-related tasks and questions is to adopt a “Unix-like” philosophy. Unix is one of the OG computer operating systems, developed in the 1960s and 70s, and it laid the foundations for much of modern computing. One of the central tenets of Unix is that software tools should do one thing and one thing well. Consider the `ls` command-line tool. It lists the contents of a folder. That’s it. That’s all it does. The `grep` tool finds specific text patterns in a document. That’s it’s job. The `wc` tool counts the number of lines, words, and characters in a text. You get the idea. Unix prioritizes small, simple tools that can work together – if the user needs them to! – over large, complex ones that try to do it all, regardless of whether the user needs them to do it all.

When we apply this thinking to data tools, we ought to value those that answer a single question well. The most obvious version of this, in my mind, is the on-demand reporting that many student information systems offer. You want to know who was absent today? That’s report *ATT-101*. You want to know which students are currently considered “chronically absent” for the year? Report *ATT-102*. You want to see a summary of grades for marking period 3? Report *GRD-207.*

All of these reports were created to answer specific questions. That's why there are lots of them, because they all do different things. Whereas the mega-dashboards that plague education today aren’t created to answer *any* questions. They’re created to jam as much data as possible, filterable by as many cross-sections (e.g. student race/ethnicity, EL status, grade level, school) as possible into a single tool. It doesn’t matter if it’s *useful* data; it just needs to be *more* data, so some company can sell it to your school division.
