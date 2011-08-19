All software has an inside and an outside. The inside is where the software makes decisions about what it's supposed to do. The outside is what we call the "interface" and it's how you interact with the software &mdash; whether "you" is a person sitting at a keyboard or another piece of software. For the rest of this piece I'll be using "interface" to describe all kinds of software outsides whether they're web pages, service APIs, internal APIs, etc.

If software has an interface where it interacts with something outside itself then it's a little bit like people. If it relates then it can suffer from relational disorders. An interface can be unreliable, it can be slow, it can be too verbose, etc. I'm going to model a specific type of software interface disorder and use a human psychological model for it.

> Narcissistic Personality Disorder
> A narcissist lacks empathy; is unwilling to recognize or identify with the feelings and needs of others.

# Narcissistic Software

The other day a sweet, blue-haired old lady was sharing her stories with me. "And my cousin Veronica, y'know, she had that condition for years. And her son, Bryan, after that horrible accident, was just never the same". I've never heard of Veronica or her son before. I don't know what condition Veronica suffered, nor what Bryan was like before (or after) this mysterious accident.

This lady, sweetheart though she is, was demonstrating narcissism as she told the story. Narcissism, in the technical sense, is a failure to distinguish that one's reality is subjective and that other people have experiences distinct form yours even in the same culture, company, and family.
She had an internal understanding of the world that included her memories, her relationships, and her judgements and she (temporarily) forgot that my experience of the world is different from hers. I don't know those people in the story. I know other people that she doesn't know. If we're to have a conversation we have to talk about people we both know. Or one of us can tell a story that introduces a new character but we have to give extra information so that we both know enough for the story to make sense.

Narcissism is not gazing longing at your own visage in the mirror. That may be the origin of the term from a Greek myth but it's used very differently in modern psychology. To get a better feel for Narcissism just imagine a 4-year-old kid jumping into a swimming pool saying "Hey, watch what I can do!" but nobody ever pays attention. Then picture that kid all grown up and still looking for that same "Hey, look at me!" validation of their self and their worldview from everyone they meet. Their constant focus on self and their own inner reality prevents them from growing the psychological muscles necessary to imagine other people's distinct inner selves.

Interesting note: Narcissistic Personality Disorder is very common in America but psychologists in other cultures report never having encountered a single case. Other cultures often generate totally different disorders.

Okay, let's switch gears and apply that human model to software interfaces.

Narcissistic software doesn't sanely relate to other software. It doesn't know the difference between its inside and its outside. It doesn't have a grasp of how other services, clients, libraries and people will need to use it. More specifically: It is coded without sufficient thought given to how it will be used.
 
## Exposing internals inappropriately

One way for an interface to be narcissistic is for it to expose it's internal workings in an unhelpful or even dangerous way.

See if you can find a problem with this (contrived) narcissistic interface:

    http://example.com/list_users?sql="select * from users;"

Okay, so problem #1 is that some joker at a computer will edit this url to read sql="drop table users;" and destroy the data. But that security problem is really just indicative of the larger issue that the inside and outside of this app have been confused with each other.

This user-listing service assumes that, because it uses SQL internally, SQL is an appropriate language for the outside world as well. But what works inside this application is a poor fit for outside.


## Having Expectations Versus Explaining Clearly

My therapist once told me that "children have expectations but adults make requests." This includes adults who have the emotional maturity of children. A child knows it has a need and, if they are at a stage of [age-appropriate narcissism](http://en.wikipedia.org/wiki/Narcissistic_personality_disorder#cite_ref-DSM-IV-TR_0-1), they will expect that other people intuitively understand this need. Part of becoming an adult is learning to communicate needs and expectations clearly in terms that other people can comprehend. Please don't ask my wife how slowly I'm learning this lesson.

Again, this applies well to software. I don't even have to contrive an example for this because it's so common.

Without good documentation, an interface (even a well-written, secure one) is narcissistic. And I mean _good_ documentation. That's README's, tutorials, screencasts, and books, in that order. Automated docs are worthless. They don't distinguish important parts of code from unimportant ones. They don't distinguish commonly-used functions from rare cases. They don't give you examples of usage and common mistakes. They just prettify the software implementation that is inherently internal.

Man pages are even worse. Very few man pages teach someone how to use a program, they only list the possible options one can give grouped by type. There's no mention of common use cases or gotchas. They feel most like a usage reference for the developer of the program than an actual manual. Man pages are like if someone asked you to describe yourself and you responded by listing everything you'd ever done. "Was born, ate pizza 853 times, have bachelor's in biology, etc." It's useless. If you want to know about a person (or a piece of software) for the very first time you need the person/software to imagine what you care about (maybe they have to ask) and form an answer that meets your needs succinctly.

> If you disagree with me about man pages being awful, I dare you to adjust your hard drive with the `dd` command using only the man page for help.

A narcissist knows if they like something but they're unable/unwilling to figure out if you like it to. They can tell what they're interested in but don't know if you feel the same. Software, to avoid this pitfall, must take into account what will be making use of it's outsides and how. It needs to reflect a good understanding of expected usage.

If the software you're writing is worth using then it's worth giving it a sane interface. The externally-accessible parts shouldn't be tied to it's internal structure and it should have clear, human-written documentation about how it should be used based on your best guesses of how it will actually be used. The internet is not a network of computers, it's a festival of relational applications. Our code only gets invited to the party if we teach it to relate well to it's peers.
[I'm a little confused here again on if the software is relating to other apps, or to people. FWIW, it seems both of those types of relating are worth investigating. What is a narcissistic UI like, and how is that different from a narcissistic API?]

