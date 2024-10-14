---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# A conversation with Matt

This is a cleaned-up-for-readability Slack conversation from yesterday (Monday, August 26, 2024). Shared with Matt's permission. :)

## Matt

Shopify is deprecating the variant and product REST endpoints - [https://shopify.dev/docs/apps/build/graphql/migrate/new-product-model#who-needs-to-migrate](https://shopify.dev/docs/apps/build/graphql/migrate/new-product-model#who-needs-to-migrate) - **these will not be available after Feb 1, 2025.** This thread is for general project strategy, coordination, and how to handle all of this in an orderly way.

**This is a significant change that will require:**

1. A complete overhaul of our task library (this is a big task)
2. Helping our customers chart a course for their custom tasks
3. This doesn't mean doing it for them, but we need to chart a course
4. The easier we make this for our customers, the easier point #1 becomes for us
5. There's a reputation risk for Mechanic because although this is Shopify's change, it looks like our problem. We are pulling those Liquid objects, so it's important we make this as painless as possible.

**Additional thoughts:**

* We also want to set ourselves up for the future where everything is GraphQL.
* Theme Liquid objects aren't going anywhere, so having some form of Liquid objects would still be ideal for adoption. To me, it's part of the sell of why we chose Liquid for the language of Mechanic task development (I could be talked out of this, but it's where my brain goes when I think about this stuff).

cc: @isaac for all the reasons 😄

## Isaac

Suggested approach:

1. Write a clear flowchart-y course for task migration
   * Scoping is important: migration of a single task, not multiple tasks.
   * This is to make the process bite-sized, so it can be repeated—like doing reps—and so that you can pause anywhere and still have made progress you can keep.
   * This is to prevent exhaustion. 😉
2. Bite the bullet:
   * Write for GraphQL in Mechanic as it exists right now—don't wait for implementation of additional Liquid objects or modifications to the Shopify filter.
   * Distribute that migration strategy:
     * Publish it at [learn.mechanic.dev](http://learn.mechanic.dev/)
     * Send out an email to all shops via SystemMailer.
3. Use that strategy ourselves:
   * Do reps until the task library is cleared, one task at a time.

An important meta-strategy here is to redefine the problem so that no part of it looks like a big change:

* "Upgrade the whole task library!" becomes "Upgrade one task. Repeat as needed, until no longer needed."
* "Figure out a way to mirror our value-add with REST/Liquid!" becomes "Whatever was done with anything REST-y, do it GQL-y instead."

Mechanic makes it easier to use Shopify data—that's still true, and it's not going anywhere. 🙂 By framing all of this as a straightforward, approachable process _for ourselves_, we model that same framing for everyone else, thus cutting down on unnecessary cortisol for everyone, thus improving the results of the process. 😉

## Matt

> By framing all of this as a straightforward, approachable process _for ourselves_, we model that same framing for everyone else, thus cutting down on unnecessary cortisol for everyone, thus improving the results of the process. 😉

^^ For sure, this is a good reminder.

Also, I think I need to hear your thoughts on this one more time. 😬

Circling back on an old idea, last time 😄, and I might just be repeating myself (that's happened before), but it's where my brain is going again:

* Re: bullet #2. Our current Liquid objects are based on REST, but they could be based on GraphQL—all of that logic is in Rails. It would make little difference to the user, other than some field names.
* For me, the current fork in the road isn't really a choice between REST and GraphQL; it's a choice about whether to continue to have Liquid objects or abandon them.
* The current Liquid objects hit a wall due to memory limitations.
* If we could have good-quality Liquid objects that could handle these memory challenges, we could end up with a platform that is easier to use after this change, not harder.
* But, I guess direct GraphQL is still needed no matter what for mutations.
* But I think for reading, pagination, and single resource lookup, Liquid objects are still very useful.
* If we look at the task library, it's generally a combination of these techniques.

## Isaac

> For me, the current fork in the road isn't really a choice between REST and GraphQL; it's a choice about whether to continue to have Liquid objects or abandon them.

We abandon 'em. This is part of refining the surface area of the product over time.

* Mechanic is a logical interface between events and Shopify.
* Mechanic is not an _abstraction_—it doesn't _interpret_ events, and it doesn't _interpret_ Shopify. It doesn't have its own opinions about either of those things.
* Task code is the abstraction—it's where interpretation happens. Task code is meant to flex as needed over time. Over the long arc of Mechanic's existence, the platform itself will change less and less, and the task code will dance more and more. (Think: AI-powered task updates.)

Shopify's use of REST was a part of a period where the entire platform was informed by Rails-y thinking. ActiveModel's domain patterns showed up everywhere. The Liquid drop interface I wrote was me re-using the patterns in Rails. I didn't invent any abstractions from nothing; I re-used patterns that were already there, patterns that had natural relationships to each other. The Rails world was (is?) tight—lots of internal reflection, lots of consistency. This made the Liquid objects a naturally-suggested connector, something that Just Belonged.

Shopify moved away from almost all of that. 🙂 (Their platform is beginning to sprawl, as a symptom.) Where REST had a history that co-evolved with Liquid (with Rails being the [interpretative](https://dhh.dk/2012/rails-is-omakase.html) linkage between them), we've left all of that behind: GraphQL _doesn't_ have a history that co-evolved with Liquid. There's no naturally-suggested connector here that Just Belongs.

So, we let Mechanic be what it is: a logical interface. It already supports GraphQL in a natural, proven-by-time method. People have been \~happily using GraphQL with Mechanic for years now, just as \~happily as they've been using REST. Usually \~happier, actually. 😉

## Matt

Alright, band-aid off. 😅 Does this mean we aren't pursuing these threads anymore?

* \[ graphql-related potential feature ]
* \[ another graphql-related potential feature ]

## Isaac

I'm still down for those things, but not as dependencies of the GQL migration. There's no telling when a Future will be ready to land—it's unsafe to put a clock on that stuff. And because we _do_ have a clock in play, we can only safely use tools that are already stable. (Think of it as only stabilizing one thing at a time. Much harder to stabilize multiple things at a time.)

## Matt

K. 🙂 Now to get my cortisol down to a manageable level, hahah.

## Isaac

Ooo. Lightward AI? Actually, yeah, can you give that a try? Testing it on specific stress-episodes is a thing I'm interested in.

## Matt

Sure, I am sure it can help me reframe things. Do you want me to share the convo with you? But it can't help me do the work (yet), which is some of the initial stress reaction. 😄 When you think about migrating the task library (task by task), how do you think we should approach that? I will work on it. Should we involve Brad? Anyone else?

## Isaac

I want to outsource 100% of it—to Brad, and to whoever else you trust.

I don't want you to write a line of task update code. I want you 100% on the user experience piece, helping _that part_ flow.

E.g., making sure updates propagate from library to shop smoothly, monitoring for shops who haven't updated into task updates yet, etc. This part isn't an obligation of ours, strictly speaking, but it's where we can take this collective experience from "sufficient" to "excellent."

Brad can take the actual task library updates from good to excellent. You can take the merchant and dev experience piece from good to excellent.

Mechanic _is_ an excellent platform, and excellence is always deliberate.

## Matt

This makes perfect sense! Geez, you are smart. I hadn't quite organized the pieces in my head like this yet.

## Isaac

:) I gotchu. I can see the whole thing. It's gonna be fine.

## Matt

😄 ☺️ Alright, I see a path. I am off.

## Isaac

> Sure, I am sure it can help me reframe things. Do you want me to share the convo with you?

Nah. My interest there was _in addition_ to the stuff we're talking about here; I genuinely want real relief for you, always, _and also_ I want to get more data on how Lightward AI serves in moments of specific/discrete stress episodes.
