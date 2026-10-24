+++
date = '2026-10-23T21:30:24-04:00'
draft = false
title = 'Learning Is Now Optional'
+++

I was looking at my Github profile recently, and I noticed that [one of my pinned (and most starred) repositories](https://github.com/ekholme/gcp_quarto_api) is a step-by-step guide for deploying an API to Google Cloud that can render parameterized Quarto reports with data analyzed using R. I wrote the guide 3 years ago after struggling to build an internal tool at work that created class-specific reports for teachers.

Now, 3 years later, this type of tutorial feels so, so obsolete. If you’re a data scientist in 2026 and you need to build a tool like this, you just ask your AI model of choice, and it will happily build it for you.

Maybe I’m looking back at the past with rose-tinted glasses. Maybe I’m romanticizing the bygone days of searching Stack Overflow and scouring random blogs and Github repos for clues and little snippets of code I can steal. But it makes me a little sad that I could complete this project in an afternoon now. 

What I’m most sad about is that, in the age of AI coding, learning has become optional.

My background is in quantitative research and statistics – not computer science or web development – so when I had to build the GCP-Quarto-API tool I needed, I had to go out and learn about Docker and how to write an API and CI/CD and all of the idiosyncracies of Google Cloud products and how to deploy R code on Google Cloud, which Google doesn’t officially support with their first-party libraries.

I had to comb through Stack Overflow and find problems that were kinda sorta similar to mine and figure out how to generalize the solutions to my problem. I had to traverse the byzantine GCP documentation pages. I had to write code that I knew would fail and then decipher the error messages to figure out why it was failing.

In short, I had to learn.

Today, I can ask Claude to figure it out, then go get a coffee while he chugs merrily along. I don’t even need to know what Docker is to get a working solution, much less how to securely mount secrets to my Docker container. Today, I could deploy a better tool than I did 3 years ago and learn precisely nothing in the process.

The learning, rather than the producing, has always been the most appealing part of the work for me. Obviously, nobody is paying me solely to learn. My job is to produce things that are useful for others. In some cases, those things are data tools (dashboards, models, visuals). In other cases, those things are reports. But learning was always, or almost always, a beneficial side effect. Need a model estimating the effectiveness of some intervention? Cool, I get to brush up on causal inference methods. Want a dashboard showing student achievement data? That’s an opportunity to better understand how JSON web tokens work.

Now, learning is no longer an implicit part of building something new, at least if I’m using AI. I have to go out of my way if I want to ensure I’m actually learning, rather than simply producing. This mostly entails hand-coding side projects or little exercises intended to teach (or reinforce) a specific topic. 

The irony, of course, is that AI is also a great tutor. I’ve been writing a [psychometrics library](https://github.com/ekholme/eePsychometrics.jl) in Julia to refresh myself on classical test theory and item response theory, and I’ve been using Claude to get feedback on my code and to ensure I’m understanding the concepts correctly. But I don’t let it write any code for me.

Maybe that’s just the world we live in now, where learning and creating things are more or less orthogonal. As long as we can be intentional about protecting time devoted solely to learning, I suppose this is ok. Who knows, it may even be a more efficient way to learn. But it just doesn’t feel as rewarding.     

