---
layout: post
title: Narcissistic Software
permalink: write/narcissistic-software.html
published: true
author: Jack Danger Canty
author_url: http//jackcanty.com
---

# Software Psychology: Narcissism

Software is like people. It has an inside (where it makes decisions
about what to do) and an outside (where it tries to work and play well with others). We call the outside of software "the
interface". We just call the outside of a person "the face".

So let's diagnose software problems using the tools we've built to
diagnose people.

<fieldset>
  <legend>Narcissistic Personality Disorder</legend>
  A narcissist lacks empathy; is unwilling to recognize or identify with the feelings and needs of others.
</fieldset>

# Narcissistic Software

Narcissism is not gazing longingly at your own visage in the mirror. That may be the origin of the term from a Greek myth but it's used very differently in psychology. A narcissistic person cannot distinguish that their reality is subjective and that other people have experiences distinct from theirs. If someone has ever told you a story where they referenced unknown people and places as if you should know what they're talking about then you know what talking to a narcisisst is like. It's frustrating because you must do all the work of figuring out the missing pieces in their story. And you have no chance to share your own subjective reality with the narcissist.

 To get a better feel for Narcissism just imagine a 4-year-old kid jumping into a swimming pool saying "Hey, watch what I can do!" but nobody ever pays attention. Then picture that kid all grown up and still looking for that same "Hey, look at me!" validation of their self and their worldview from everyone they meet. Their constant focus on self and their own inner reality prevents them from growing the psychological muscles necessary to imagine other people's distinct inner selves.

With me so far? Okay, let's switch gears and apply that human model to software interfaces.

Narcissistic software doesn't sanely relate to other software. It doesn't know the difference between its inside and its outside. It doesn't have a grasp of how other services, clients, libraries and people experience it from the outside. More specifically: The software author did not give sufficient thought to how it will be used.

## Software Extraction Lifecycle

Most code will, if indefinitely maintained, go through an extraction
lifecycle that looks like this:

* Code begins life as a script for a specific task
* Code is organized properly into objects, functions, or whatever
  paradigm the language uses for naming behavior (also, tests are nice)
* Code is separated into multiple, well-named files
* Code is extracted into its own project where it can be loaded with a
  single command
* Code is documented
* Client libraries are written for specific anticipated clients
* Clients are documented

In the early stages the software is totally narcissistic. It can barely
get its own job done so it doesn't waste time thinking about the
experience that others have of it. Any user will have to read the source
to work with the software. But as it matures through the
lifecycle it grows in usability and starts to express itself more
clearly. The documentation and client libraries are the final step in
anticipating the user's needs and meeting them.

If the code we write is good and useful then it should be maintained. If
it's maintained then it should eventually reach the point where it
becomes relationally healthy and sheds its narcissism. If you have code
that performs some important task but that has stopped maturing in these
ways then I'd strongly encourage you to consider why. Is it actually
that important? If so, helping it along the extraction lifecycle will
reveal new flexibility and accessibility in your project.

## Having Expectations Versus Explaining Clearly

My therapist once told me that "children have expectations but adults make requests." A child knows it has a need and, if they are at a stage of age-appropriate [narcissism](http://en.wikipedia.org/wiki/Narcissistic_personality_disorder#cite_ref-DSM-IV-TR_0-1), they will expect that other people intuitively understand this need. When we adults hold unspoken expectations rather than making verbal requests we act out of a leftover childhood narcissism. Part of our growth is to shed this expectation and learn to communicate our needs in ways other people can comprehend.

Again, this applies well to software.

Software has needs. It has requirements and expectations of you, the
user. But it needs to make those needs extremely clear or it will be
narcissistic software.
Without good documentation, an interface (even a well-written, secure one) is narcissistic. And I mean ****good**** documentation. That's README's, tutorials, screencasts, and books, in that order. Automated docs are worthless. They don't distinguish important parts of code from unimportant ones. They don't distinguish commonly-used functions from rare cases. They don't give you examples of usage and common mistakes. They just prettify the software implementation that is inherently internal. You'd be better off reading the source.

Unix man pages are even worse. Very few man pages teach someone how to use a program, they only list the possible options one can give grouped by type. There's no mention of common use cases or gotchas. They feel most like a usage reference for the developer of the program than an actual manual. Man pages are like if someone asked you to describe yourself and you responded by listing everything you'd ever done. "Was born, ate pizza 853 times, have bachelor's in biology, ..." It's useless. To learn about a person (or a piece of software) for the very first time you need the person/software to imagine what you care about (maybe they have to ask) and form an answer that meets your needs succinctly.

> If you disagree with me about man pages being awful, I dare you to adjust your hard drive with the `dd` command using only the man page for help.

To avoid narcissism in your software, write it with a good understanding of anticipated usage by people who are not you. If the software you're writing is worth using then it's worth giving it a sane interface. It should have clear, human-written documentation about how it should be used based on your best guesses of how it will actually be used.

## Why I Care, And Why You Should Too

The internet is not a network of computers, it's a festival of relational applications. Our code only gets invited to the party if we teach it to relate well to it's peers. You and I, as engineers, have much to offer &mdash; but only if we remember that other people need to use our code.
