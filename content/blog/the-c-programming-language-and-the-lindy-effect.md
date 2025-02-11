+++
title = "The C Programming Language and the Lindy Effect"
date = 2025-02-11
+++

Disclaimer: This is not intended to start a flame war about C or C++ or Rust or whatever hot new programming language is the $CURRENT_THING.

This is simply an observation, open for discussion.

Here’s my proposal:

I believe C will remain widely popular in the coming decades (assuming AI doesn’t reshape our entire world by then) due to the Lindy Effect. Let me explain what this means, and why I think so.

## The Lindy Effect

The Lindy Effect is a theory popularized by [Nassim Nicholas Taleb](https://en.wikipedia.org/wiki/Nassim_Nicholas_Taleb), which has the following proposition:

The longer a non-perishable thing (in this case technology) currently exists, the more likely it will continue to exist into the future.

In other words this means if something has been around for a while, that doesn’t necessarily indicate it’s going to be out of vogue soon — in fact, the opposite can apply. I think this applies to C.

## The C Killer

Every new low-level language that comes out is touted as a C killer, or intended to replace C. These languages often have more features, better DX, different ways to handle memory, or something else.

Yet, C continues to exist — but not really even just exist, it continues to thrive.

In social media, we speak of network effects. Many who tried to leave X/Twitter in mass exodus eventually returned, because whether you like it or not — there’s no point being on a social media website if no one you know is on it. That’s the power of network effects.

With C, it is still being used to write the Linux kernel. The C ABI remains pervasive, and is used by myriad different modern programming languages. Even C++ is still growing in popularity on the TIOBE index, despite the fact it looks like an absolute monstrosity to begin learning to an outsider like me.

Think about this for a second. C has been out fifty years.

*Fifty* years.

Think about how much has technology has changed over that time. Surely something would have come out to replace it by now.
Yet even languages like Rust, which yes, I’m sure most will argue is more of a C++ replacement than a C replacement — still remains relatively niche. Even C++ which was intended to be an “improvement” on C failed to replace it.

I think it’s easy to put this down to “C is going to be legacy code”. People are used to the tools they are used to. But I think it’s something more than that.

The longer something is about, the more polished and generally available resources are (which helps adoption). It’s stable. The more information There are decades worth of mistakes to learn from, and therefore easier avoid for newer learners. It’s small — it lives up to the UNIX philosophy of ‘do one thing and do it well’ (which has also stood the test of time, by the way). The tooling is rich. It’s cemented itself in the industry, so the more it will be around, regardless.

What I really think the question is, or what people actually mean when they go about comparing these programming languages and talking about C and Rust, is actually “will it be a giant waste of time if I learn language X instead of Y?”

And the reason I make this, is because I don’t want people to be put off learning C because of this. I only know a little bit of C, and it still feels very important to me.

## But, but, what about Rust?

To be clear, I’m betting on Rust succeeding as well — both things can be true at once.

A lot of greenfield projects will likely pick up Rust, and it’s made plenty of inroads into big tech companies like Microsoft.

In fact, Rust is almost 10 years old now — so it will also be interesting to see if we see the Lindy Effect in action with Rust itself, keeping Rust in circulation for a long time too (I think this is likely).

The main thing I’m trying to get at here, is that question I mentioned: why waste time learning something that could be "legacy" soon?

People online like to speak in absolutes, likely because it lands them the most clicks or garners the most attention. I hate to be a boring fence-sitter, but frankly, I think both sides are wrong.

Rust users like to make out that learning C is “useless”, and you should only go and use Rust. C enthusiasts on the other hand have their happy little greybeard bubble, plugging their ears and shouting “lalala” like Rust doesn’t exist and won’t ever be relevant.

Here’s my thesis:

- C will continue to remain massively popular in embedded and operating system development. If you have to write everything in unsafe, then you’ve defeated the main selling point of using Rust in the first place.
- Rust will lead many greenfield projects in areas where C/C++ was previously popular; including but not limited to high-performance computing, browsers, database, critical software infrastructure, etc.

The main takeaway from my post is that I think people, especially us as programmers or technology enthusiasts, think way too far ahead. We’re already asking the question — will Rust replace C? When instead, we should probably thinking more like “what do I want to spend my time on for the next six months?”.

When even if this was the fact, it would still take decades for it to fully happen. I don’t think we can honestly tell what the next two, let alone ten years will look like as the rate of technology changes so fast. Instead of trying to pick optimally, pick based on your own circumstances — what industry you wish to work in, which language interests you the most, which has the documentation or resources you find the most useful, whether you want (or need) a package manager, etc.

We’ll see if this thesis holds.

Thanks for reading.