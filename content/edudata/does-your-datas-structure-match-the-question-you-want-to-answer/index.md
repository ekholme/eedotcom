+++
date = '2025-03-07T13:00:24Z'
draft = false
title = 'Does your data’s structure match the question you want to answer?'
+++

I have this thesis that people in education often get frustrated with data – or they feel like data is useless – because the structure of the data they’re collecting doesn’t allow them to answer the question they want to answer. This usually happens because someone – a principal, a social worker, a central office administrator, a teacher, whoever – is trying to take an existing report or data product and apply it to their question. The problem is that these reports and data products weren’t designed to answer that specific question. Often, they weren’t designed to answer any question. Many data exports, especially those from learning apps, are just broad, shallow, generic slop that tell us little more than how much time a student spent on an app. Or the reports are compliance-y things that someone is required to submit to fulfill some program guidelines or state mandates.

A more sinister case than the data being obviously useless, though, is when the data in some off-the-shelf report or export *nearly* tells us what we want to know, but it’s off by *just enough* that it ends up being useless, but in a non-obvious way. That is, the content is sorta kinda almost what we need, but the structure is not quite right.

Let’s use attendance as an example. Since COVID, attendance – or, really, absenteeism – has been one of the biggest problems that schools have faced. And vapid think-pieces and half-baked solutions about “fixing chronic absenteeism” have been just as prevalent as all of the vapid think-pieces about “AI in the classroom.”

Either way, basically every school or school division has access to some canned report in their student information system that tells them about how many absences each student has. There are probably some slight differences in how these reports look, but *generally* they look something like this:\

| Student ID | Excused Absences | Unexcused Absences | Total Absences |
|------------|------------------|--------------------|----------------|
| 12345      | 1                | 1                  | 2              |
| 23456      | 2                | 5                  | 7              |

And when you create the report, you’ll generally have some options regarding the start date and end date you want to limit the report to, and maybe a few other canned filters you can apply. Cool, great.

Unfortunately, lots of people spend lots of time looking at these sorts of reports. I say this is unfortunate because these reports…don’t really help us answer meaningful questions. The structure of this report all but precludes any sort of meaningful analysis.

*Brief interpolation – I don’t blame the people on IT/data services teams for making this type of report. It probably does fulfill some compliance obligation, or else someone in a leadership position asked them to make the report, and these IT/data services teams get so many requests that they can’t possibly be the value-arbiters of all of them (plus that’s also not really their job).*

Anyway. We can see that student 23456 – let’s call him little Tom Buchanan – has 7 absences. Maybe being absent 7 times triggers some intervention. Tommy B has been absent a lot, so we’re going to have a school counselor or social worker or someone call home weekly and check in with Mr. and Mrs. B. Or do something similar that ought to get him to school more often. Great.

How do we know if this intervention is working?

Well, if we download the report again, it’ll tell us Tom’s cumulative absences (in the specified window). Which doesn’t help us, because what we actually want to do is compare his absences pre-intervention to his absences during the intervention and/or after the intervention. Just looking at cumulative absences tells us nothing about the effectiveness of the attendance intervention. So, we’d have to download the report twice to be able make this comparison. And not only do we have to download the report twice, but we'd need to join the data from these two reports together to make the comparison. In this simple case, this “joining” could simply be writing down the numbers on, like, the back of a napkin and then just looking at them, but it usually won’t be that straightforward. And obviously this back-of-napkin evaluation isn’t methodologically rigorous, but it’s not a terrible approach for a one-off, ad-hoc analysis.

But so now what if we have multiple students who are receiving some attendance intervention, and we want to know if it’s working for each of them? It would be extremely unlikely that they all began the intervention on the same day (think of the poor social worker making that many calls!). Say we have 40 kids on this intervention, and they all started on different days. We’d need to download 80 (!) different reports, each with a slightly different start date/end date window specified.

I realize this will reek of white-collar privilege, but hell is manually downloading dozens of .csv files. I'd rather be gnawed on by Satan in the 9th circle of hell than click through dozens and dozens of pages to download reports.

But I digress. What we actually want – what can actually help us answer a question that informs what we do for little Tom B and students like him – is data structured like this:\

| Student ID | Date   | Attendance      |
|------------|--------|-----------------|
| 12345      | 9/1/24 | Present         |
| 12345      | 9/2/24 | Excused Absence |
| …          | …      | …               |
| 23456      | 9/1/24 | Present         |
| 23456      | 9/2/24 | Present         |

Or something similar. This format allows us to easily count the number of absences before or after any arbitrary date, for any student. The downside of this structure is it requires the end-user to do a little bit of number-crunching on their end. If you’re working in Excel, probably a VLOOKUP to join in the intervention dates, plus some filtering and pivot-tabling. Nothing crazy, but also not nothing.

The upside is that it’s, you know, useful.

What’s more is that this second structure is probably what the data actually looks like in your student information system (SIS) database – it gets turned into the first table in a report. What that means is that it’s remarkably easy to make the second report. 

I imagine end-users don’t think much about what the structure of the database tables looks like…because that’s not their job. But the unfortunate side-effect of this is a naive adherence to the reports that already exist, or to slight tweaks on the reports that already exist, and then trying to squeeze these stones until they yield water.
