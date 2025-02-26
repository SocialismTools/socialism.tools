---
title: Chapter-in-a-box, four years later
publish: true
tags:
---
## or: what you need to know before deploying open-source software to your chapter

*originally published in 2023, lightly edited from original version*

Energized by the Bernie campaign, I joined the National Tech Committee in August 2019. While writing this post, I found a document from June 2020 where I had some of the first recorded thoughts on what a Chapter-in-a-box (CIAB) project would look like.

The goal of CIAB was to have a simple way for most of a chapter’s tech needs to be met by open-source software, and have a wrapper around all the software (or a box) to make deploying, securing, and updating it easy. At the time, I thought it could be a huge leap forward in improving DSA’s wild west of tech infrastructure. I kept seeing suggestions that DSA use more open-source software and thought CIAB could be a catalyst to broad FOSS adoption in DSA.

For example, a chapter could rent a Linux VM from a provider like Digital Ocean, run a script or follow a simple tutorial, and have critical services like email, SSO, document editing, file hosting, chat, and so on ready to go. There were existing FOSS apps that did all these things already, so how hard could it be to tie them together into a nice package?

_(It’s okay to laugh at this point)_

This would differ from the current tech strategy of most DSA chapters, which is to use free-as-in-beer SaaS tools as much as possible and fork over high prices for those tools when using the free version is not possible. There were a ton of great tools that existed to serve each of these user cases, and several promising management solutions, so I thought it was well worth the time to get hands-on and try them all out. If I found even a handful of tools that met our needs, I thought we could accelerate digital collaboration across the org at a time when the world was shutting down.

Over the following years I’ve tested many different FOSS tools (along with other comrades like [Aslan](https://discussion.dsausa.org/t/chapter-in-a-box-project-megathread/18384)), talked to at least a dozen people about how they use FOSS in their chapters, ran the WordPress project at the NTC and served on the SC for ~two years. I know there’s a lot of energy among the techie left out there, and I want to help share what I’ve learned, so others can learn from my successes and avoid repeating my mistakes.

![](https://socialism.tools/wp-content/uploads/image-3-814x1024.png|100)

From Rafael romero on [Unsplash](https://unsplash.com/@rafa_gold)

## why CIAB is a bad idea

The full realization of the CIAB dream – one secure, managed, FOSS platform covering multiple apps like file hosting, chat, content creation, and so on – is simply not possible given the current software ecosystem, and even if it was, it would still a terrible idea to have every chapter own their own tech stack. There is simply not enough available tech labor on the left to make this work – it has to be centralized, and even that would be very difficult.

Let’s break down “why CIAB is a bad idea” into a few categories.

### money money money, it’s so funny

Free apps are expensive! An old phrase in the open-source community is “Free as in beer” in contrast to “free software”, referring to the difference between a free commodity (something you consume, but don’t engage with – like a free beer) and the community-first ideal of open source. Later on, we also got [free as in puppy](https://opensource.com/article/17/2/hidden-costs-free-software) – the idea that open-source software is free of monetary cost but requires significant investment (as in actual dollars as well as effort) to continue functioning properly. Through the “free as in puppy” view, the CIAB project wants to give DSA chapters a box full of not just one, but a dozen little costly responsibilities pissing all over the virtual carpet.

Almost every free app DSA might use, like Mattermost or Nextcloud, expects to be installed on their own VM when looking at official instructions. The costs – monetary and logistical – of this add up fast, especially when the apps won’t tolerate tiny VMs. Many of these apps have dockerized versions, but then you need someone who understands docker to set everything up, and the dockerized versions of apps sometimes have performance or feature regressions. Many projects look easy to set up at first glance but reveal some nasty cracks in the foundation when used (ask me how I know).

Before you even start using an app, you – the sysadmin – have to navigate these hosting and configuration options and figure out which one will give you the least headache. And don’t forget that whatever method you choose better have an easy way to apply updates, or you’ll be repeating the whole process again soon (you might think this is obvious and would be included in the docs for everything. You would be wrong).

I also hope you didn’t install this software on a computer at home, or you’ll need to port forward and possibly work around limitations imposed by your ISP. Contrast this to SaaS software that logs you in instantly for free, and while the limitations of free accounts may chafe, they are clear and usually predictable.

But let’s say you’re really committed to using FOSS. There are a few different pieces of software that propose solutions to this problem, the two biggest being Cloudron and YunoHost. YunoHost is a great community effort that still falls short in many important ways for CIAB’s purposes – it requires a fair bit of manual configuration to work properly, isn’t as polished as Cloudron, and has all the same drawbacks.

We’re going to use this for mission-critical work, so we choose Cloudron, a professional platform used by several large organizations. It only costs ~$300 USD a year, which is a great price for the functionality it offers. This alone is a great example of why we have to centralize tech – the licensing model for all software companies is cheaper when centralized.

Let’s pretend we bypass all of these problems – [Cory Doctorow](https://twitter.com/doctorow/status/1454158218117197826) writes DSA a fat check to pay for all of our hosting costs and hires full-time tech staff to maintain the apps. What are the other issues at that point? Let’s go back to our free puppy analogy.

![](https://socialism.tools/wp-content/uploads/rodion-kutsaiev-6W8H4puOJB0-unsplash-1024x819.jpg)

Photo by [Rodion Kutsaiev](https://unsplash.com/@frostroomhead?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash) on [Unsplash](https://unsplash.com/photos/white-paper-roll-on-white-table-6W8H4puOJB0?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash)

### the free puppies are ugly…

Let’s be honest for a moment: free software designed for end-users is substantially worse than their paid counterparts. Even in cases where the free version is more popular it’s (usually) not _better_. Every time an alternative to these apps is mentioned, even when someone uses it every day or for their work, they will admit it’s simply not as good.

It’s not the developer’s fault, though. Apple, Adobe, Google and Microsoft have billions of dollars to hire world-class engineers and designers. They spend millions of dollars a year on user research. FOSS apps simply cannot compete with this.

### …and there’s not many of them to choose from

For most categories of app, there are one or two major FOSS competitors if you’re lucky. For document collaboration, there are basically two major players, and both are unsuitable for use in DSA. Groupware – email, calendar, contacts services – and document collaboration are some of the two most important pieces of software any entity runs. They are also where the CIAB dream goes to die.

#### dashed upon the rocks of docs

Let’s first look at the most popular FOSS office software, LibreOffice, assume you installed it alongside Nextcloud and LibreOffice Online, and that someone is paying an experienced admin to babysit it. Right at the start, this is three pieces of software, from separate companies, to match a tiny fraction of the function of Office 365 or Google Workspace.

LibreOffice is woefully inadequate for how the modern left utilizes document and collaboration software. According to contributors, the codebase is [not in good shape](https://www.theregister.com/2020/07/16/libreoffice_ecosystem_beyond_utterly_broken/) and this is not surprising to almost anyone who has attempted to use LibreOffice. Here’s the main reasons why LibreOffice is a non-starter:

- **Local-first editing has been out of style for a decade for a reason**. Collaboration is critical to every DSA workflow I’ve seen, and cloud-based editing (Google Docs) makes it so much easier. It helps prevent people from losing documents if their computer crashes and they forgot to save, it makes sharing as easy as sending a link or plopping a doc into a folder, multiple people can be in a doc at the same time, and when your editor is online-first sync conflicts are extremely rare.
- **LibreOffice is still local-first**, the web version is developed by a third party, Collabora, with [licensing restrictions](https://www.collaboraoffice.com/subscriptions/) that would technically require DSA to pay for it around $22 per user per year (the average DSA member pays $27 in annual dues). Even if we somehow got LibreOffice Online for free, the issues don’t stop.
- **LibreOffice is ugly and difficult to use.** I get pushback on this point from people in the FOSS community, but it’s true. Look at how cluttered LibreOffice is compared to Office or Docs right when you open a file. Compare the features to Office and the ease of use to Docs. If you don’t think it’s ugly or difficult to use for your needs, that’s fine – but that is a minority opinion.
- **Mobile is an afterthought.** The Document Foundation doesn’t have mobile apps for LibreOffice, but Collabora has one. It’s very bad. I haven’t seen anything that suggests The Document Foundation has any plans to change this.
- **It’s buggy.** LibreOffice desktop apps, Collabora Online, the mobile apps, the _website_ _itself_ are buggy. No software is perfect, but LibreOffice is noticeably bad in this regard.

*on re-reading this, the above might sound mean to LibreOffice - I didn't intend this to rip them to shreds, it's not their fault they don't have a near-monopoly to pay their developers with. This is unfortunately the nature of open source*

The other main alternative in the office collaboration space is [Cryptpad](https://cryptpad.org/), which has all the above issues except one – CryptPad is cloud-native and end-to-end encrypted! CryptPad is getting funding from some EU grants, so they have a solid financial base to work from, and the cloud-first end-to-end encryption model is compelling and unique. Time will tell if they can pull it off – if they do, they’ll have LibreOffice to thank.
### almost nobody cares about FOSS

Let’s start off with something obvious: many FOSS advocates support FOSS because of the ideology – it’s not just about the software experience FOSS apps provide.

Normal people (who do not know or care about how software is made) **do not care about FOSS**. Most people don’t know what FOSS means or are only vaguely aware of it. Basically every device or software product people choose in their everyday life is not FOSS. This is not a coincidence – people want stuff that is easy, available, and does what they want.

It is true that many people care about their privacy. There are three big problems with turning this feeling into action. The first is that many people _say_ they care about their privacy but value a long list of things above their privacy (environmentalists are very familiar with this kind of pain). The second is that normal people aren’t tech experts and don’t even know how (and how often) their privacy is being violated in the first place. The third is that even if they learn, most fixes are difficult to implement, which can make people feel helpless.

*Just how hard is it to protect your privacy? [This blog post](https://www.optoutproject.net/data-free-disney/) about a privacy-conscious mom who wanted to go to Disneyland with her family but not submit her family to tracking is a spectacular example of how pervasive tracking technologies have become, how little the average person even notices them, and how difficult it is to avoid tracking even for committed techies. Leftists should understand that the fix to systemic problems will not be addressed by individual consumer choice.*

To be clear, I’m not saying you should throw your privacy to the wind and give Sam Altman your eyeball scans or whatever. But we need to work with what we’ve got. Skills like enabling 2FA and ad-blockers, skills for spotting scams, and using a password manager are all far more likely to have a positive impact in the average person’s life than complicated cybersecurity tactics designed only to foil a potential FBI investigation.

The same goes for collaboration software. It’s an extremely tough sell to convince comrades to use a costlier, clunkier product that needs far more attention and money to maintain properly. The basics of Google Drive are (and will almost certainly remain) free indefinitely. **Do we want organizers spending tons of time managing, learning, and otherwise spending time on software, or do we want them doing something more productive?** In an ideal world, we can do both, but we aren’t there yet.

![](https://socialism.tools/wp-content/uploads/image-2.png)

Screenshot of the [toot](https://fasterthanli.me/articles/just-paying-figma-15-dollars#draw-io-the-good) that inspired me to finally get this out of drafts.

## CIAB is dead – long live CIAB

Most DSAers are using free (or cheap) Google/Microsoft accounts already. For DSA chapter leadership purposes, only a single account needs to have a paid Workspace license to get the major benefits it provides. I don’t think it’s a coincidence that many chapters gravitated to Google Docs/Drive for most of their needs. They need tools that work, and the Google suite works best given our requirements.

Given all of this: if you have software that works for you, is free (or cheap), everyone you collaborate with already knows how to use it, and it does what you need it to do – why would you ever switch to a FOSS product you need to pay more for, have someone maintain, is harder to use, and might not do what you need? You wouldn’t! So don’t worry to much about it – yet.

The good news for nerds into FOSS is that there are already a handful of FOSS apps in use at DSA. WordPress, that old standby, runs many of our national sites, and chapter websites uses a constellation of FOSS developer tools. We’ve used Discourse as our forum software for several years, the forum software of choice even among people willing to pay for forum software. We’ve recently set up and tested Open Slides, a very exciting piece of meeting software (yes, really!) currently used to run meetings and hold votes for major German political parties. Many DSA-ers rely on Signal to talk to their comrades as well.

What these tools have in common is that they are in use widely already thanks to solid features and UX, have solid financials, either from enterprise sales, donations, or government grants, and are easy to maintain centrally or cheap enough to have maintained for us. Chapter in a box may not be workable, but a DSA powered by, and giving back to, the FOSS community is.

## socialism dot social

It has been really, profoundly positive for me to work with so many different comrades across the country. Working together is rarely easy. There are political debates, bureaucratic roadblocks, resource constraints, and so on. But what political organization in history hasn't had these?

And sometimes you get a win and it feels great to have made a difference. We now have working groups using a new, more powerful and easier-to-use WordPress platform, chapter websites are getting dozens of chapters a rock-solid web presence, we launched Open Slides to very positive reviews, we have a [new newsfeed](https://feed.dsausa.org/), and there’s work being done to engage chapter leaders more on tech issues via the new tech liaison program. The NTC has had plenty of headwinds, but we’re still growing and getting stronger every day.

As for CIAB, the dream lives on, albeit in a dozen pieces. Maybe one day DSA will be big enough to put them together. Until then, the work continues – one piece at a time. If you want to help put the pieces together, [join the NTC](https://actionnetwork.org/forms/dsantc-signup/) and help us build the tools to power democratic socialism in our time.

_If you’re a DSA member, continue signing up for [monthly dues](https://act.dsausa.org/donate/membership/). If you’re not a member yet, consider [joining](https://act.dsausa.org/donate/membership/)_ _the largest socialist organization in the US to fight for Medicare for All, a Green New Deal, and more._

---

**Bonus problems**

*The FOSS login nightmare*

Every major business in the world has switched to Single sign-on (SSO), a broad set of complicated technologies that means users only need to remember a **single** password to **sign on** to all their apps. SSO solutions like Okta also include robust 2-factor authentication solutions to keep accounts secure.

While Cloudron has very broad app support, not all apps support Cloudron’s LDAP login. LDAP doesn’t natively support 2FA, which is a massive security issue. Cloudron added TOTP-based 2FA to their LDAP solution but only some apps support it. Admins would also need to manually manage users in the several apps that don’t support LDAP, which can be confusing and time-consuming for both admins and users.

Outside Cloudron, only a handful of individual FOSS apps support SSO. Many FOSS apps have a hybrid licensing model and lock SSO behind an enterprise license – assuming it’s available at all.

As many large enterprises learned the hard way, identity and access management is tough, and having a single sign-on (SSO) solution is critical to keep users and admins sane.

*So you're concerned about the surveillance state*

One major point of pushback you’ll get from techies when recommending that people continue to use the free, easy tools they like is that these tools are cloud hosted and therefore not secure. The state can get access to your Google Docs with an easy-to-get court order, yes. This isn’t nothing, I don’t mean to downplay the danger of the state.

**But** all the alternatives to Docs don’t stop the state from sending you a letter demanding your data or breaking down your door to get it or tossing you in a cage. If you get to the point where the FBI is after you, _you are in very deep shit_ and I’m not convinced your choice of collaboration software will be the make-or-break change in your life. If you intend to do any cool, fun crimes, _do not ever talk about them on the computer._

Also, think about what is more likely: you become Edward Snowden 2, or you misconfigure a setting on your self-hosted document cloud setup and get hit with ransomware or something. From the smallest companies to the biggest mega corps, everyone is always getting bit with infosec issues because it’s very, very easy to fuck up.