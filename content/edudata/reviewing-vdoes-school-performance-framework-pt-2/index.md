+++
date = '2025-02-21T13:00:09Z'
draft = false
title = 'Reviewing VDOE’s school performance framework (pt 2)'
+++

In my last post, I wrote about the mastery component of Virginia’s new school performance framework. I’m more or less optimistic about that component of the framework in that it’s straightforward to calculate and the weighting of different proficiency levels feels generous (particularly when compared to a binary pass/fail approach).

This post is about the growth component of the framework. I’m…less optimistic about this component. To be honest, it kinda sucks.

Let’s start with what the component is, and then I’ll get into why the implementation is garbage.

------------------------------------------------------------------------

The [growth component](https://www.doe.virginia.gov/home/showpublisheddocument/58394/638665703423370000) (the link contains FAQs) of the [school performance system](https://www.doe.virginia.gov/state-board-data-funding/accreditation-accountability/school-performance-and-support-framework/spsf-overview) is meant to measure the extent to which students are growing (academically, not, like, physically) as much as they “ought” to be. At least in math and reading, between grades 3-8. The motivation for measuring growth is a good one. Content mastery is an important goal, but it’s not a sensitive enough measure for many students. Consider a student who enters 5th grade reading on a 2nd grade level. It might be unreasonable to expect her to be reading on-grade-level by the end of the year, but we hope she grows “enough” academically throughout the year. Inversely, consider a student who enters 5th grade reading on an 8th grade level. This student is already mastering 5th grade content and could probably pass the 5th grade SOL reading assessment with minimal instruction. But we still hope that she, too, grows “enough” academically throughout the year.

So this concept of measuring growth, then, is meant to ensure that schools are helping students learn, irrespective of where they are in relation to grade-level standards.

The idea is laudable, but putting it into practice is tricky. First, you might have noticed that in the last few paragraphs, I referred to students growing “enough” or as much as they “ought” to, and these terms are intentionally hand-wavey and vague. There are two ways to operationalize “growing enough.” First, you can set *criteria* stating that a student who starts at X should end at Y, a student who starts at Y should end at Z, etc. This is hard, because there are many many many different “starting points” – even if you use relatively few prior  tests to determine a “starting point” – and it would require lots of domain-specific knowledge and consensus among domain experts (and this sort of consensus is rare among education researchers).

You can also use *norms*, which means that rather than expecting students to meet some predetermined growth criteria, we simply expect students to grow as much as students similar to them (with similarity based on their previous test scores). This is a much easier problem to solve, because we can eschew all of the content-area experts and consensus and whatnot. Instead, we just need a large-enough and diverse-enough dataset, one that also contains students’ prior test scores, and we can have a statistical model predict how much a student ought to grow by using their prior test scores along with the actual growth of all of the other similar students in the state.

In a broad sense, there’s nothing intrinsically wrong with a norm-referenced approach to testing. Lots of tests use this approach, including the SAT and the Stanford-Binet intelligence test (the IQ test), among others. But I do think there’s a problem in using this approach in a mandatory statewide accountability system.

First, norm-referenced tests are essentially zero-sum instruments. In this system, a student’s “expected growth” is the average amount of growth (as measured by Virginia’s reading or math standardized assessment, the SOL test) of all similar students. So – and this is an oversimplification of the process & the math, but the logic holds – to estimate how much a 4th grade student who scored 400 on her 3rd grade reading SOL should grow, this system would take the average growth of all other 4th grade students who scored 400 on their 3rd grade reading SOL. If, on average, this group scored 402 on their 4th grade reading SOL, then we’d expect our student to score a 402.

You might remember from statistics classes that, assuming scores are normally distributed (the distribution is bell-shaped), half of all scores will be below average and half will be above average. In this growth system, then, about half of all students will not meet their expected growth because, statistically, about half of all students will be below average. Because that’s how averages work.

This seems ok for something like college admissions, where people are competing for a limited number of slots in selective colleges. It seems bad for a mandatory statewide accountability system where there is no reason for this competition.

It’s also not hard to imagine cases where this type of test yields wonky results. Imagine that, for some reason, every school in Virginia just opted not to teach students but the state still gave the SOL tests in the spring. Students could learn literally nothing, and about half, under this system, would demonstrate “greater than expected growth.” Inversely, imagine that Virginia implements a new statewide reading curriculum that’s absolutely incredible, and students statewide learn, on average, 3 years worth of content in a single year. Under this system, a student who learns *only* 2.5 years of content would demonstrate “less than expected growth.”

These cases are both extreme hypotheticals, but they still illustrate the basic problem of an accountability system that awards points to a school – or withholds points from a school – based on what other schools do.

------------------------------------------------------------------------

The other big issue has to do with how different amounts of growth are weighted within the system. You can see the weights for different amounts of growth (relative to expected growth) on page 8 of [this calculation guide](https://www.doe.virginia.gov/home/showpublisheddocument/58428/638682177064430000). To better understand these weights, let’s take a quick detour into what *standard error* is.

The standard error (SE) is, generally, the error associated with any statistical estimate. It’s similar to the *margin of error* that we often see in the context of polls. When we estimate any quantity, the standard error is an attempt to quantify the amount of uncertainty in our estimate.

In the context of these growth models, the statistical models are attempting to estimate a student’s expected growth, so the standard error is a numerical acknowledgement that this is the best estimate the model can make (for the given student), but there’s still error implicit in the whole estimation process.

A related principle that builds upon the concept of standard error – and one that is central to the whole statistical enterprise – is that there’s no real reason to treat scores falling within plus-or-minus (+/-) one standard error (or, often, +/- two standard errors, depending on the case) as any different from the expected value. Consider a poll. If a poll estimates that John Jackson will receive 55% of the vote in an election (the expected value), and the poll’s margin of error is 1%, then the poll is really saying he’ll likely receive somewhere between 54% and 56% and, more to the point, that there’s no real reason to consider, say, 54.5% as any different from 55.0%, since they're both within the margin of error.

So, getting back to student assessments, imagine a student’s expected score on an SOL test is 410, but the standard error is +/- 5 points. If a student earns a 408, that’s less than 410, but it’s still within one standard error, so there’s no reason to treat this student as if she didn’t meet her expected score. That’s the whole point of the standard error.

And yet! If we look at the weights that VDOE set, scores between the expected growth and +1 standard error earn 1.0 points, whereas scores between -1 standard error and the expected growth earn 0.5 points…even though there’s statistically no reason we should think about any scores between +/- 1 SE as different from one another. And if you look closely at the visuals on the [EVAAS](https://www.sas.com/en_us/software/evaas.html) website (note – EVAAS is the statistical model, created by [SAS](https://www.sas.com/en_us/home.html), that Virginia uses for its growth modeling), you can see in the red-orange-green-blue band thingy that the green band – WHICH REPRESENTS +/- 1 STANDARD ERROR – extends symmetrically around the midpoint (the dotted black line, i.e. the expected growth):

![](https://www.sas.com/en_us/software/evaas/_jcr_content/par/styledcontainer_6813_1970687728/par/styledcontainer_2124397250/par/image_copy.img.png/1722536168934.png)

In other words, the literal statisticians who built the model don’t differentiate between any scores within +/- 1 SE. But Virginia’s school performance system does.

This decision is…questionable…on its own, but what tips it from questionable to sketchy is the weightings assigned to different amounts of growth. We should assume that students’ actual growth scores will be normally distributed around their expected growth (i.e. the residuals are normally distributed). That is, the model won’t be perfect, but most actual scores will be close to the expected scores, and there should be roughly as many actual scores above the expected value as there are below. The *scores* should be symmetric around the expected score. But the VDOE’s school performance system *weights* are asymmetric. The result is that, if the growth scores within a school shake out as we’d expect, that school would earn approximately 71% of the points available within the growth component.

That is, if the actual growth scores are normally distributed around the expected growth, we’d assume ~16% would be below -1 SE, ~34% would be between -1 SE and expected growth, ~34% would be between expected growth and +1 SE, and ~16% would be above +1 SE:

(.16 \* 0) + (.34 \* .5) + (.34 \* 1) + (.16 \* 1.25) = ~.71

If we think about this in terms of a letter grade, then schools that are growing students at the rate we expect them to would earn a low C. Maybe this feels warranted to some people? I suppose you could make an argument that performing at an average level warrants a C, but it feels overly punitive to me, and I’d wager that most people don’t think of a C as an average grade anymore. Plus, let’s not forget that this has as much to do with how students in other schools perform as it does with how students in my school perform.

------------------------------------------------------------------------

Overall, the growth component of Virginia’s school performance framework feels icky to me, and that some folks who designed it are subtly twisting statistics to push a political narrative.
