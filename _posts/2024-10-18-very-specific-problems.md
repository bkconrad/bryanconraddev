---
layout: post
title:  "Very Specific Problems"
date:   2024-10-18 03:11:23 +0000
categories: devops tech
---

I've been thinking of Very Specific Problems today (VSPs for short). You know:
the kind of problem that involves enough specific elements that it can't be
usefully googled. Getting library A to work with framework B using third-party
service C. That sort of thing.

Looking back through my career, the most time-consuming "bite sized" tasks have
all been VSPs. I had another one this week. Somehow I had fooled myself into
thinking that VSPs were behind me because I've deliberately chosen a stack of
non-specific things that basically everyone is using. Spring with envvar
configuration on Kubernetes, that's pretty vanilla right? Or so I thought.

VSPs are such a time sink because they typically involve all of the following:
  1. Multiple complex systems interacting
  2. Advanced use cases of these systems to begin with
  3. A mixture of systems and features that make them hard to find info about

You know you've hit a VSP when you search for all the keywords involved, maybe
even an error message, and the search engine informs you that one or more of
them are missing from the listed results. In this moment you are truly alone.

<img src="https://imgs.xkcd.com/comics/wisdom_of_the_ancients.png" alt="relevant xkcd">

## Solving a VSP

If you find a VSP, there are some pretty good strategies to solve them. The
first thing to do is ask every colleague you can find. Yep, even the juniors (do
we have juniors anymore?). VSPs rarely have complex solutions, it's more often a
trivia question that you didn't know you were being asked. So ask anyone who
might know some relevant trivia to get started.

If the team trivia quiz doesn't work, now you need to formalize your question
and ask as many people as possible. I follow the ancient techniques of asking a
StackOverflow question (do people answer StackOverflow questions anymore?).
Create a minimal repro case. State exactly what the expected result is, what the
observed result is, and what you've tried. Send this to anyone familiar with the
systems involved. Hell, you might even try actually posting it to StackOverflow.

A quick note here on AI assistants. I haven't had many VSPs since they've been
widely available, but at least in theory an AI assistant is ideal for solving
them. They *should* have precise knowledge of these systems and the ability to
identify and answer the relevant trivia question. Unfortunately the few times
I've tried this they've produced confidently wrong answers. Twice I was able to
spot the fluent bullshit, but I have taken the bait once and wasted time by
believing an AI answer. It's worth trying, but be highly skeptical of whatever
it tells you.

Once you've run out of people and things to ask, you're left to debug. Debugging
is beyond the scope of this writing, but you'll be familiar with it from your
development work. Instrument anything you can and step through it line-by-line
testing all of your assumptions. Anything you can't run in a debugger has to be
instrumented as much as possible. Think about `strace` and `-v` flags, set the
log level to `DEBUG`, anything that will give you a view into what's going on in
there.

Then you have to start testing your basic assumptions. Does the file actually
exist? Is the config value really not set? Try removing whatever components you
can to pare it down to the simplest most minimal environment you can for
tinkering. Your automation skills come in handy here as you formalize and
isolate the problem into smaller and smaller pieces. You hopefully already know
this part of the process.

## Avoiding VSPs

The best way to deal with a VSP is to not encounter one in the first place. The
best way to do this is to keep your problems very searchable. Pick the most-used
frameworks and tools. Follow the official documentation as closely as possible.
Odds are, the thing you're trying to achieve is not particularly novel so try to
accomplish it in the most boring way you can.

One unfortunate aspect of VSPs is that they become more visible as your
technical skill level increases. As you learn more about the capabilities of
your tools and how they can be applied to innovatively solve problems, you're
definitionally going to a place where few people have been. Here, you should
heed the age-old technical advice of not being too clever. Beyond that, you sort
of have to accept that it comes with the territory.