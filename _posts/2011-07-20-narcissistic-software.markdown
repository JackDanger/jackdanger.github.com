---
layout: post
title: Narcissistic Software
permalink: write/narcissistic-software.html
published: true
author: Jack Danger Canty
author_url: http//jackcanty.com
---

# Narcissistic Software

The other day a sweet, blue-haired old lady was sharing her stories with me. "And my cousin Veronica, y'know, she had that condition for years. And her son, Bryan, after that horrible accident, was just never the same". I've never heard of Veronica or her son before. Nor do I know what condition Veronica suffered or what became of her boy.

This lady, sweetheart though she is, was demonstrating narcissism as she told the story. Narcissism, in the technical sense, is a failure to distinguish that one's reality is subjective and that other people have experiences distinct form yours even in the same culture, company, and family.
She had an internal understanding of the world that included her memories, her relationships, and her judgements and she (temporarily) forgot that my experience of the world is different from hers. I don't know those people. I know other people that she doesn't know. If we're to have a conversation we have to talk about people we both know. Or one of us can tell a story that introduces a new character but we have to give extra information so that we both know enough for the story to make sense.

Narcissistic software doesn't sanely relate to other software. It assumes that other services, clients, and libraries understand it's own internals. It doesn't know how much of itself is or should be accessible to other software. And it can't comprehend what experience other software will have relating to it.

## Confusing the View from Inside with the View from Outside

All software has some portion of itself that's accessible from the outside and some other part that isn't. The externally-visible part is considered the 'interface' even if the distinction between the parts is unintentional. The inside part may use languages and patterns that make sense within the domain of the software but are not appropriate elsewhere. Here's an unintentional interface that fully exposes the internals of an application for external use:

    <form action='/app.php'>
      <input type=hidden name='sql' value='update users set updated_at = NOW() where id = 6' />
      <input type=submit value='Update Account' />
    </form>

The obvious problem with this is that a visitor will delete the app's database just for fun. But the real design problem is that the interface is narcissistic. This application can't distinguish it's insides from it's outsides and expects that other software will speak the same languages as it does internally. Any software that doesn't speak SQL can't relate to this app. Any software that does speak SQL will relate to this app in unexpected (and tragic) ways.

## Having Expectations Versus Explaining Clearly

But many interfaces properly separate internals from visible externals. These interfaces are finite, well-organized, and complete in that they offer a full set of features so you can write software that uses them. They may even have good security, unlike the example above. These good interfaces are still narcissistic if they don't properly explain themselves.

One of the symptoms of [Narcissistic Personality Disorder](http://en.wikipedia.org/wiki/Narcissistic_personality_disorder#cite_ref-DSM-IV-TR_0-1) is patients expect other people to implicitly understand the patient's needs and abilities without being told. Healthy people make clear requests of others and share their experiences in terms that other people can relate to. Narcissists just have unvoiced expectations of other people (that usually go unmet).

Without good documentation an interface (even a well-written one) is narcissistic. And I mean good documentation. That's README's, screencasts, tutorials, and books. Automated docs are worthless. They don't distinguish important parts of code from unimportant ones. They don't distinguish commonly-used functions from rare cases. They don't give you examples of usage and common mistakes. They just prettify the software implementation that is inherently internal. Man pages are (nearly) as bad. Very few man pages teach someone how to use a program, they only list the possible options one can give grouped by type. There's no mention of common use cases or gotchas.
This is like if someone asked you to describe yourself and you listed everything you'd ever done. "Was born, ate pizza 853 times, have bachelor's in biology, etc." It's useless. You need the person to imagine what you care about (maybe they have to ask) and form an answer that meets your needs succinctly.

If the software you're writing is worth using then it's worth giving it a sane interface. The externally-accessible parts shouldn't be tied to it's internal structure and it should have clear, human-written documentation about how it should be used based on your best guesses of how it will actually be used. The internet is not a network of computers, it's a festival of relational applications. Our code only gets invited to the party if we teach it to relate well to it's peers.
