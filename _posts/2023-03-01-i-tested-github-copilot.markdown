---
layout: post
title: "I Tested GitHub Copilot and This Happened"
description: "Wondering if GitHub Copilot is right for you? In this article, I share my thoughts and experiences after using the tool for 30 days."
author: "Fabian Stadler"
categories: [tech,journal]
tags: [tools]
image: assets/img/github-copilot.jpeg
image_description: "An image of the GitHub Copilot logo."
permalink: 2023/01/i-tested-github-copilot.html
lang: en
---

It was in late 2021 that I first heard of Microsoft's new AI coding tool, GitHub Copilot. It was the first major news for me after the [controversial acquisition of GitHub by Microsoft](https://news.microsoft.com/2018/06/04/microsoft-to-acquire-github-for-7-5-billion/) and the well-known mass exodus to other platforms like GitLab.

Back then, AI as a technology was already picking up and created a comparably small hype. [AlphaGo](https://www.deepmind.com/research/highlighted-research/alphago) from Google DeepMind had been making headlines between 2015-2017 for defeating several pro Go players. A bot from [OpenAI showed a victory at The International 2017 Dota 2 tournament in 2017](https://qz.com/1052409/openai-just-beat-a-professional-dota-2-player-at-the-international-2017). Later, Google announced its AI-assisted tool Google Lens, which millions of people use on their smartphones.

Still, this hype was far from what we have now, as most of these were only demonstrations but provided no breakthrough improvements in people's everyday life. This changed in 2020, when OpenAI released their Generative Pre-trained Transformer 3 (GPT-3) and showcased a wide range of capabilities. These included the generation of various texts, code generation, question-and-answer type scenarios, and more.

From then on, it was only a matter of time until people found their way to use AI for a wide range of use cases. A major boost came from OpenAI, providing a beta with free credits that made it possible for almost everyone to try out their API for the above tasks. Like many people, I got in touch with GPT-3 for the first time through memes and funny text generation attempts by other people.

Now, as an engineer, code generation was the most-interesting use case for me as I knew of many tasks that were simple and repetitive to code but still cost some minutes or a quick search on Stack Overflow. If we had a tool just to make these tasks obsolete, it could already save minutes if not hours every week, reducing workforce cost by several hundred dollars per person every month.

The only problem I had was that my first attempts with the OpenAI beta were unsatisfying. The UI provided interesting and often good results for small prompts, but it was difficult to produce excellent results for large context. Often, we want to generate helper methods within classes that already exist and retain variable names and conventions. This meant if it produced an unsatisfying result, one had to restore and alter the entire prompt again. Soon, my general opinion was that AI in this state was only helpful in generating simple things.

## GitHub Copilot - A Game Changer?

GitHub Copilot was first announced and released as a technical preview in June 2021, with access initially limited to a small group of developers. As of March 2022, GitHub Copilot became available for Microsofts IDE Visual Studio. Later in June, GitHub ended the technical preview, and made Copilot available as a subscription-based service for individual developers. The tool is still in development and has been receiving regular updates and improvements since then.

From then on, GitHub Copilot quickly rose to the #1 discussion topic and caught the attention of almost all developers. The expectations were high. People wondered if it would change the industry, but many also worried about layoffs through automation. It was so omnipresent that it was annoying. And since my experience with GPT-3 was unsatisfying, I did not really bother trying it out when I heard about many issues. 

One of the bigger ones was copyright. Since I felt connected to the open-source community and knew of the problems that AI produces with our current copyright laws, I found it very controversial. Especially DALL-E, another AI model by OpenAI, which generates images of text prompts based on scraped images, was in parallel, very much in disrepute, because many artists felt powerless and robbed. 

## ChatGPT and The Second AI Hype

Now, as the discussions about GitHub Copilot declined, another AI-model made its way to popularity. And this time, the AI hype was real. With ChatGPT, OpenAI published an improved version of their previous models as a free research version at the end of 2022. Now, everyone could easily access AI without restrictions. The use cases were unlimited. Even for OpenAI, the hype came so unexpectedly that the free UI is to this day under heavy load, and they could open a paid service with more stable access.

While media companies were quickly to hop on this hype train, ChatGPT became one of the big news topics. This also meant that many companies were thinking how they can make use of AI not only as a service for analysis but also to improve their own development. Microsoft made a major investment in their partnership with OpenAI, creating huge expectations of many future AI-assisted services that companies have access to.

This leads me to the actual topic of this article, namely my own experience with GitHub Copilot. In order to find out more about its capabilities, I had the chance to try out the trial during the last month. Thus, I tested the AI-assistant in different scenarios and thought a lot about it.

## The Basics of GitHub Copilot

First, how does GitHub Copilot actually work? The setup is very simple in principle. All you need is a GitHub account. If you already have an existing account or have created a new one, you can now go to the [GitHub Copilot](https://github.com/features/copilot) page and sign up for the free trial version by clicking on "Start my free trial".

![Start A Free Trial of GitHub Copilot](/assets/img/github-copilot-homepage.png){:style="float: center"}

They will guide you through a procedure where you have to enter some personal data. This includes your address and a credit card or a PayPal account to prevent misuse and to collect future payments if you want to use the service for a longer period. Otherwise, the trial ends after 60 days and is free.

Once you have done that, everything else is very simple. In Visual Studio Code and in Visual Studio, there are plugins that can be easily installed from the Marketplace. For Visual Studio, you need to upgrade to a newer version if you don't have it installed yet. Of course, there are similar plugins for other IDEs as well, but I have only tried it for these two IDEs so far.

### Code Suggestions

Now let's move on to the use of GitHub Copilot itself. GitHub Copilot is automatically enabled after you install the plugins. But how do you work with it? It's actually quite simple: The best thing to do is to create a new local repository for the first tests and create a new main class or function in some subdirectory. Alternatively, you can use an existing repository or even a loose script file.

As soon as you program, automatic suggestions for further code are generated and displayed. This works analog to existing code completion features.

![Writing A Hello World Function with GitHub Copilot](/assets/img/github-copilot-hello-world-test.png){:style="float: center"}

It usually takes a few letters to display a meaningful suggestion. GitHub Copilot is guided by what it reads in, in the above example, the function name, which already clearly suggests that now "Hello World" should be output.

What this means for development with the tool is that you should always be as specific with function names as the code you want to have. GitHub Copilot is not the holy grail that already knows what the complete code should look like based on the class name. You also have to guide the tool a bit.

However, you don't always want to create a 120-character function name so that the tool knows what it's supposed to do. Therefore, you can help yourself with comments. Either you specify in the docstring exactly what the function should do.

![Hello World From With Loop Docstring](/assets/img/github-copilot-hello-world-hundred.png){:style="float: center"}

Or you can use Copilot line by line and always write a comment first and then get a suggestion for the next lines.

![Hello World With Loop From Comment](/assets/img/github-copilot-hello-world-hundred2.png){:style="float: center"}

Now, some may wonder if GitHub Copilot can also be used contextually, and the answer to that question is an emphatic yes. Copilot can also give original suggestions within existing classes.

On the one hand, it can expect new features and thus proactively contribute.

![Context Suggestions With Copilot](/assets/img/github-copilot-hello-world2.png){:style="float: center"}

As before, you can also start defining a function, making Copilot complete it.

![Hello World From Context](/assets/img/github-copilot-hello-world3.png){:style="float: center"}

Again, give as much information as possible if you want the function to be appropriately complex.

### AI-assisted Documentation

Another feature that simplifies the work with Copilot is the documentation of existing code. This means that you write a function or already have one and then let GitHub write the docstring for Copilot. This very often saves you a lot of time that most people save by not documenting. With Copilot, it's a matter of seconds.

![Copilot Used To Create Docstrings](/assets/img/github-copilot-hello-world4.png){:style="float: center"}

If you want to enforce a specific syntax for the docstring, you can do that by giving GitHub Copilot some guidance.

![Copilot Used To Document Parameters](/assets/img/github-copilot-hello-world5.png){:style="float: center"}

In the above example, you can see that by specifying the section for the arguments here and inserting a tab, you get the corresponding variable with a comment. Unfortunately Copilot is not yet so good to create the complete docstring with all parameters. So you have to guide a little.

How good the documentation will be in the end is, of course, a matter of taste. But Copilot is an excellent assistant that makes a lot of things faster and it is better to document weakly than not at all.

### Generated Unit Tests

Finally, I would like to point out a very worthwhile use case for me. This is because GitHub Copilot is not only great for actual code or documentation but also for testing. As with documentation, unit tests are often unpopular with developers because they cost time and have to be rewritten anyway if we make major changes. If you don't work with TDD, you rarely test expectations, but things you already know work. Whether this makes sense, everyone must know for themselves. At least for regression tests, it makes a bit of sense.

So now when we create a test and import pytest into it in Python, for example, we can first define a function that returns "Hello World". As soon as I want to implement a new function, I get a test automatically generated. 

![Unit Tests With GitHub Copilot](/assets/img/github-copilot-hello-world6.png){:style="float: center"}

Of course, this works not only when implementing functions directly but also with imported modules. Even more complex tests are possible if you specialize them properly. But often you have to write your own fixtures. But then Copilot can write a good unit test with the information from the fixture and a little guidance.

## The Reviewer's Perspective

Now that I've explained the basic functionality of GitHub Copilot, which I find interesting, a comment from me on its general use. As we've already seen, GitHub Copilot is powerful and takes previous code completion features to a whole new level, enabling the generation of complex code within context.

But what does this mean for the developer and their work with such tools? Well, after thinking about it a lot, I have concluded that the developer is increasingly taking on the role of a reviewer. By that I mean that we as developers need to think less about simple implementations, and instead worry about accurate documentation and conceptual design first. Then we have code written based on this concept and only check if what it gave us is good or if it needs to be reworked.

This approach is like an architect or lead developer designing a program using UML and in text form. The developers then take care of the code and submit it for review. There, they check whether the quality is right, whether things need to be adjusted, even optimized, and so on. What we publish and use in the end is usually up to the person responsible.

For us, who use services like Copilot, this means that we are clearly responsible for what we publish. As many already know, Copilot can also generate faulty or even unsafe code. Often, you don't get the desired result either. So it's up to the developer to examine the code thoroughly, test and optimize it manually if necessary. Even a tool like GitHub Copilot cannot replace an experienced developer. But it can support.

We need to be aware of what we accept as an excellent result in advance and make decisive changes during development to achieve our desired result. So it becomes even more important to build a good foundation and enforce it consistently. Without this foundation, even GitHub Copilot cannot create us an exemplary service or program.

In the worst-case scenario, this can lead to inexperienced developers using AI tools like GitHub Copilot to create poor and unsafe solutions that find their way into production systems. As before, it is up to the reviewer to analyze and find these weaknesses. Just trusting that people who develop with GitHub Copilot will create good code would be foolish.

So, nothing will change soon in terms of the current distribution of roles. But maybe the efficiency boost can already save a job or two. Perhaps cost savings can leave more money for more developers. In the end, it could even lead to more positions. However, from my point of view, I can't say that at the moment.

All I can say is that it takes away some tasks like documentation, unit testing, and repetitive code that you often write, such as recursive functions, much faster. This saves me a lot of time even when I'm developing, and potentially a lot of time for customers.

GitHub Copilot currently comes in [two versions](https://github.com/features/copilot#pricing) for individual developers at 10 dollars per month and for enterprises at 19 dollars per month per license. Now let's assume a developer costs a company around 100 dollars per hour, then the tool only needs to save one-fifth of a single hour of time in a month to pay for itself. Just having a few features documented can save that amount of time. As I wrote before, I expect it can save several hundred dollars per month per person. However, Copilot will certainly not remain the only service that offers such features. Otherwise, Microsoft could charge much more.

## Controversies and Concerns

Now that I've compiled all my thoughts, there's one more issue I'd like to discuss here. And that is that my experiences above are simply for an unbiased viewpoint, without criticizing what else the developer is giving away in rights with GitHub Copilot or how Copilot should be legally classified. Also, I have not yet addressed the business risks posed by services like GitHub Copilot.

First, as I mentioned at the beginning, there is the copyright controversy. What is meant by this is that [GitHub Copilot was trained on public repositories](https://www.theverge.com/2022/11/8/23446821/microsoft-openai-github-copilot-class-action-lawsuit-ai-copyright-violation-training-data). Including those that came with inheritable licenses that allow users to link or use code in their own repository only if the same license is used. This is very common, especially for open source software, as people rarely want free code to become commercial.

For this reason, there is a legal dispute, which probably has little chance. GitHub refers to its own terms of use, which contain a note that GitHub may use the data hosted to improve its own services. However, I cannot answer how this looks legally correct, as I am not a lawyer.

The fact is, however, that as with DALL-E, which allows users to generate very similar things to those published by artists with a lot of effort and little return without reuse rights, GitHub Copilot can produce very similar code to that on which someone else holds a copyright. In rare cases, [it can even produce bare copies](https://twitter.com/DocSparse/status/1581461734665367554?s=20). Even if GitHub qualifies this.

This puts Copilot users in a [legal gray area](https://www.creativereview.co.uk/artificial-intelligence-copyright/) that will certainly have to be discussed in the coming years. The bottom line is that the user has to make sure that they do not use any code that is under copyright. In reality, however, this is almost impossible. Just as it is almost impossible to disprove that you came up with the code yourself. Especially for simple functions everyone has written before. The user of Copilot therefore contributes to the fact that we initially resign ourselves to this gray area, which can mean financial ruin, especially for artists.

Equally opaque is what it means when Copilot becomes the author. In many countries, there is [no provision for a program or a machine to produce something with copyright](https://www.theverge.com/2023/1/26/23570967/chatgpt-author-scientific-papers-springer-nature-ban). This circumstance is already being discussed with AI-generated books using ChatGPT and is not legally clarified.

Ultimately, it is not completely clear to me, as a user, what data is sent to GitHub Copilot and in what form. Of course, data security is claimed and likely this is done correctly. But there are [other metrics](https://docs.github.com/en/site-policy/privacy-policies/github-copilot-for-business-privacy-statement) that fall into the hands of the product provider, not just Copilot. So the product, like other AI tools, should be taken with a grain of salt. 

Especially if you're in a field where security is paramount. Therefore, it is probably not legally possible to use Copilot for customers or projects in which one is subject to certain secrecy without consent. The bottom line is that you are still sending code that is the property of a client to a third party. This is like outsourcing development. Again, though, I can't give a legally sound assessment, so this only reflects my opinion.

## GitHub Copilot Makes Annoying Tasks Obsolete

In conclusion, despite all the concerns and risks, I enjoyed testing GitHub Copilot and will continue to follow it. I may write some more articles on similar solutions. Still, I can't yet form a general opinion on whether using GitHub Copilot is commercially sound and how to use it legally. I think this discussion will hit many areas over the next few years and will continue to be a difficult gray area to resolve.

Nevertheless, I have to admit that tools like Copilot simplify many things and definitely save time. Especially for documentation, testing and many repetitive tasks that otherwise take up a lot of time, it is an optimal solution that will certainly get even better.

Eventually, we accept that such solutions will prevail. Because if you don't jump on the bandwagon, you'll probably be overtaken. AI services remind me of inventions such as printers and robots, which cost jobs but enabled people to work on more important things. So it remains to be seen to what extent tools like GitHub Copilot will lead to a transformation in development. However, it is foreseeable that they will contribute majorly to further development in the IT sector. At least in terms of productivity.
