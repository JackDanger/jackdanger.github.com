All software has an inside and an outside. The inside is where the software makes decisions about what it's supposed to do. The outside is what we call the "interface" and it's how you interact with the software &mdash; whether "you" is a person sitting at a keyboard or another piece of software.

In this sense software is a little bit like people. If it has to relate then it can suffer from relational disorders. An interface can be unreliable, it can be slow, it can be too verbose, etc. I'm going to model a specific type of software interface disorder and use a human psychological model for it.

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
Here's an unintentional interface that fully exposes the internals of an application for external use:
[Hm: It's a hidden input, so it doesn't "fully" expose the internals. It's not exactly clear if this is something you found in a real app, or something you made up as an example (I'm presuming the latter). If it's hypothetical, why not make it a text field, so the internal language is then directly exposed to the user? I'm not sure why this interface is an "unintentional interface": There is clearly intention to have some kind of interface here. Perhaps a smoother wording would be: Here's a hypothetical interface that unintentionally exposes the application's internal language. Then again, if it is all hypothetical, it's all intentionally crafted... In any event, I think this example needs more set up.]
   <form action='/app.php'>
     <input type=text name='sql' value='update users set updated_at = NOW() where id = 6' />
     <input type=submit value='Update Account' />
   </form>

The obvious problem with this is that a visitor, with a slight modification, could delete the app's database just for fun. But the real design problem is that the interface is narcissistic. This application doesn't distinguish it's insides from it's outsides and expects that other software [but isn't the "other" in this case, a user, not software?] will speak the same languages as it does internally. Any software that doesn't speak SQL can't relate to this app. Any software that does speak SQL will relate to this app in unexpected (and tragic) ways.
[But isn't this form mainly talking to it's own backend? or is the backend the "other" software in this case?]

## Having Expectations Versus Explaining Clearly

But many interfaces properly separate internals from visible externals. These interfaces are finite, well-organized, and complete in that they offer a full set of features so you can write software that uses them. They may even have good security, unlike the example above. These good interfaces are still narcissistic if they don't properly explain themselves.

One of the symptoms of [Narcissistic Personality Disorder](http://en.wikipedia.org/wiki/Narcissistic_personality_disorder#cite_ref-DSM-IV-TR_0-1) is patients expect other people to implicitly understand the patient's needs and abilities without being told. Healthy people make clear requests of others and share their experiences in terms that other people can relate to. Narcissists just have unvoiced expectations of other people (that usually go unmet).

Without good documentation, an interface (even a well-written one) is narcissistic. And I mean good documentation. That's README's, screencasts, tutorials, and books. Automated docs are worthless. They don't distinguish important parts of code from unimportant ones. They don't distinguish commonly-used functions from rare cases. They don't give you examples of usage and common mistakes. They just prettify the software implementation that is inherently internal. Man pages are (nearly) as bad. Very few man pages teach someone how to use a program, they only list the possible options one can give grouped by type. There's no mention of common use cases or gotchas.
This is like if someone asked you to describe yourself and you responded by listing everything you'd ever done. "Was born, ate pizza 853 times, have bachelor's in biology, etc." It's useless. You need the person to imagine what you care about (maybe they have to ask) and form an answer that meets your needs succinctly.

[Interesting point. It's like an unweighted presentation of all facts, a brutal equality that doesn't hold up the more valuable components over the others. The Narcissist thinks everyone has the equivalent view of themselves that they do, perhaps? Presumes they don't need to add emphasis to needed components that would make the components more accessible/meaningful/useful to an outsider.]

If the software you're writing is worth using then it's worth giving it a sane interface. The externally-accessible parts shouldn't be tied to it's internal structure and it should have clear, human-written documentation about how it should be used based on your best guesses of how it will actually be used. The internet is not a network of computers, it's a festival of relational applications. Our code only gets invited to the party if we teach it to relate well to it's peers.
[I'm a little confused here again on if the software is relating to other apps, or to people. FWIW, it seems both of those types of relating are worth investigating. What is a narcissistic UI like, and how is that different from a narcissistic API?]

