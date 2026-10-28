+++
date = '2025-04-11T12:00:31Z'
draft = false
title = "RAG time"
+++

I’m both an AI optimist and an AI skeptic. I use AI tools in my day-to-day work, mostly to help with coding, but with some other tasks as well. Google Gemini is one of the tabs I open, along with my email and calendar, as soon as I boot up my laptop in the morning, and I keep it open throughout the workday.

And yet. I’m not fully on board the AI hype train, especially for education. Like I wrote about a few weeks ago in [my reflection on Grammarly](/edudata/writing-for-busy-readers-and-why-not-to-use-ai/) and AI tools that support writing, it feels both shortsighted and naive to try to use AI to solve every problem. Sure, AI tools can help you produce more, but they're not going to solve issues that are, at their root, cultural, organizational, or interpersonal problems.

When ChatGPT first burst into public consciousness, I was just as susceptible to this hype as anyone else. 2 years ago, I built a proof-of-concept lesson plan generator ([here’s the code for it](https://github.com/ekholme/saul), although the tool itself is no longer available online) that could prioritize areas of instruction based on a school’s previous assessment data and generate lessons targeting these skills. Now, 2 years later, I still see some value in this strategy, but I’m also much more skeptical of it. The lesson it produces might not be any good. Or it might draw on approaches that aren’t empirically supported (e.g. learning styles) or that don’t align with your school’s or school district’s pedagogical approach/curriculum. The tool can produce a single lesson, but stringing together a bunch of independent lessons with no thought for continuity certainly isn't ideal. This isn’t to say that the tool I put together was useless, but rather that it wasn’t doing 80 or 90% of the work for a teacher, who merely had to do some light editing after being bequeathed with a lesson by some omniscient AI platform. It was doing maybe 30-50% of the work, if that, and getting its lesson plan to be something ready for the classroom still required quite a bit of expert revision from the teacher.

To be clear, there’s nothing wrong with this. It’s probably what we should be shooting for – using AI to scaffold a solution rather than expecting it to completely solve a problem.

One technique that could improve this approach, though, is [retrieval augmented generation (RAG)](https://ekholme.github.io/brain/Retrieval-Augmented-Generation), which is a needlessly complex tech-y way of saying that this technique allows LLMs to incorporate data that they weren’t trained on. The massive LLMs that tech companies like OpenAI and Google and others deploy are trained on (i.e. they learn from) large swaths of the public internet, plus also probably some non-public and/or copyrighted stuff that these companies slurp up anyway. Even so, they’re obviously not trained on things like your school district’s internal documents or your school's lesson plan template. RAG addresses this by giving us a way to programmatically retrieve and inject relevant internal documents as context into a prompt that we pass to an LLM, which allows the LLM to use those documents when generating responses.

This helps address some of the issues with AI lesson planner described above. If we can feed relevant curriculum documents – pieces of a curriculum map, unit plans, exemplary lesson plans, templates, resources, etc – that our own schools or school districts have created, we get some assurances that the lessons these AI tools produce will align with our internal pedagogical approaches and will include most of the components we expect in our lessons. They’ll also probably be better than what a generic, zero-shot prompt to an LLM would produce.

How does this work? First, we’d load our curriculum documents into a specialized database (a vector database). Next, we'd develop a prompt that we can systematically manipulate with queries and relevant documents. We (the people building the tool, in this hypothetical at least) probably want to first include some sort of preamble that describes the task to the LLM, like this:

> “You are a bot that helps teachers plan lessons using context from the curriculum materials referenced below. Be sure to respond completely, incorporating relevant information from the referenced curriculum materials. If the materials below are irrelevant to the answer, you may ignore them, but please indicate that you are doing so in your response. Please return your response as a lesson plan following {describe your lesson plan template here}”

This tells the LLM its role and tells it to prioritize the documents we’ll pass to it. The third sentence is kind of a safeguard that gives the model an out if it can’t find relevant content in the passages, but it tells the model it needs to notify us if this is the case.

In the next step, we’d append whatever question the teacher/user asked to this preamble. This might be something like, “can you help me plan a lesson for my algebra class on factoring polynomials?”

The RAG tool would then take that user question and search the database for the most relevant documents – hopefully some curriculum maps, unit plans, or lesson plans involving factoring polynomials. (If you're interested in how this works, I have some loose notes on it [here](https://ekholme.github.io/brain/Embeddings#vector-search)). And these then also get appended to the preamble and user question, so we end up with a big chunk of text (PREAMBLE + QUESTION + RETRIEVED_DOCUMENTS) that all get passed together as a prompt to an LLM like Gemini or ChatGPT, which will then be able to incorporate our specific contextual information into its answer.

Will this produce perfect lesson plans or unit plans that teachers can just pick up and use? Probably not. Could it still produce garbage? Absolutely, and especially so if your internal documents are incoherent. 

But amidst all of the AI hype that we’re all being bombarded with right now, this is one of the few approaches that, when applied to education, actually feels worthwhile to me.
