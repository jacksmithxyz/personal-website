+++
title = "Why Tailwind?"
date = 2023-06-22
+++

Tailwind tends to be one of those things that people love or hate.

The critics dismiss it for being unnecessary, forcing code duplication, and making HTML files look ugly (who wants all of those spaghetti code class tags shoved into it?)

But it’s one of those things where once you’ve  actually tried it, it's hard to go back because you can see how much more productive it makes you. There’s a reason that NextJS and TailwindCSS are pretty much the de-facto standard at new startups (at least right now). There are some caveats to this, and I still enjoy normal CSS especially with certain frameworks like Svelte/SvelteKit.

So why are NextJS and Tailwind the go-to frameworks/libraries right now?

Firstly, there is a pool of experienced developers to choose from (Next being React-based and Tailwind being relatively easy to pick up if you know pure CSS), but secondly - it’s **opinionated**. You do things the way React likes it, and you *have* to pick from Tailwind's classes and get building stuff.

This allows you or your team to get up to speed and move quickly - without having to worry about either writing pure CSS or using a stricter UI library which doesn’t give you as much control over styling.

### Locality of Behavior

There is an argument between choosing to architect software with SoC (Separation of Concerns) or LoB (Locality of Behaviour). This isn’t a binary choice where you must use one or the other; they can be chosen accordingly.

In the case of Tailwind, it uses the locality of behaviour approach. All this means is your CSS is not in a separate file to your HTML, but rather is with that element or component. A developer working with Tailwind only needs to look in a single place to find out all they need to know about the styling of a certain component.

If you need to change the styling of a button you simply open the HTML file, navigate to the button, and change the style. You don’t have to navigate to a `styles.css` or `button.css` file, search through it to find the class (or classes) it’s using and keep maybe 2+ splits open to check and adjust the styles.

Tailwind’s approach also offers more flexibility, as you can give a particular element some unique style without needing to create an entirely new CSS class for it.

The locality of behavior approach is why Tailwind works so well with component-based frameworks. Each component can have its HTML elements, styling, and functionality all within the same file and tightly packed together. This means if you look at a Button component, for example, you can immediately tell:

- How the component is structured in HTML
- The styles applied to the component
- What the component does (its functionality)

Without ever having to open up another file or look elsewhere.

Of course this isn’t a silver bullet and you're kind of already doing separation of concerns by splitting apart things into components in the first place. But it’s worth mentioning the inherent advantages of this approach.

### Code Duplication

Tailwind is often criticized for basically throwing the DRY principle out of the window, which isn’t wrong to be fair. But I think the problem tends to be more overblown than it really is.

The simplest way to deal with duplicated code you need to change (if it’s in the same file) is to just use `sed` or whatever other find and replace tools you have at your disposal. Tailwind’s documentation also mentions using [Multi-cursor editing](https://tailwindcss.com/docs/reusing-styles#multi-cursor-editing).

In the modern age of web dev, most stacks are using some kind of component-based framework as well, so managing lots and lots of Tailwind isn’t _actually_ that bad. As briefly mentioned earlier you can apply the styles to each individual component, rather than having standard HTML files with a bunch of Tailwind slapped inside of it. And if push comes to shove or you need some global styling you can always use `@apply`.

### The Locality Stack (htmx, Alpine.js, TailwindCSS)

There are a whole bunch of other reasons people advocate for Tailwind, but I wanted to focus on other aspects in this post. The biggest upside for me is undoubtedly productivity.

Some other things I’ve been meaning to try are htmx and Alpine.js. They take a similar approach to Tailwind in the sense that they focus on LoB and introducing functionality directly into your HTML.

I do wonder if all of these tools put together and the focus on LoB would become stupidly difficult to maintain or read at scale. But for smaller projects, it might be something interesting to explore instead of going for something heavier. I think they could also work well with template-focused backend frameworks like Django or Flask.

Either way, if you haven’t tried Tailwind or think it’s stupid - I hope I’ve convinced you to at least give it a try and see how it affects your productivity.

I hope you enjoyed!
