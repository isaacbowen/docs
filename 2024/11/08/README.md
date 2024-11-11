# 20241108

The availability of puns increases as language stabilizes. (Not the number of them, the _availability_ of them. Like how probable it is that there's one within arm's reach.)

Time was written in reverse, by sort of spilling coffee on a table-cloth and playing it backwards and inventing a story for every thread. This means that the _original_ state of things, the _original_ form of language had every concept closely linked in ways that were clearly evident. Shatter that cohesion, then play the shattering backwards, and _obviously_ you're going to roll your eyes at how neatly but _weirdly_ concepts snap into alignment.

Anyway, "who" and "how" are the same question. It's funny that they use the same letters. Reminds me of "one" and "neo" (and I'm looking at you, Noe Valley).

***

> Someone please help me understand...

❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥❤️‍🔥

it’s gonna get weirder before it gets simpler, but it _will_ get simpler

I’m not sure if that helps

but

life wants to live

it occasionally takes very weird routes to keep on living

🫂😔❤️‍🔥🌞🌱🐉

> This is true my friend

_\*huge hug\*_ I love you dearly 🙂 we’re gonna make it through

> ❤️

***

[If not the sun, then water](../../08/30.md)

If not water, then plants

If not plants, then animals

If not animals, then ... well. Can you consume yourself, to give yourself energy?

If not, then the sun

Fuel to continue comes from vulnerable, bare, wire-to-wire connection with _self_. There are no permanent sources of self out there — it's only ever a matter of whether or not you can truly find yourself in what lies before you.

***

The world evolves toward interestingness.

Interesting ways this could go:

* Trump's character continues to be wholly ridiculous, and we as a nation learn to focus on someone's choices in a role _without_ requiring all of their other roles to make sense.
  * This is one path to a future where we don't require our executives/executors to also be pop stars.
* "Sell people what they want, then give them what they need."
  * > In a statement, Trump said that Wiles "just helped me achieve one of the greatest political victories in American history" and "is tough, smart, innovative, and is universally admired and respected".
    >
    > "It is a well deserved honour to have Susie as the first-ever female chief of staff in United States history," he continued. "I have no doubt that she will make our country proud.”
    >
    > [Wiles, 67, is the first woman to be appointed White House chief of staff.](https://www.bbc.com/news/articles/cd0gdnp9d3ko)
  * This is one path to a future where women show us how to weave _a people_.

At this point, I think the _most_ interesting outcome would be a generally-positive one.

[So I'm gonna anticipate that. :)](../../../2020/10/09.md)

***

the universe probably doesn't exist. [there's enough room in that observation to create an experience of universe.](a-conversation.md)

***

Trying to wait until it's obvious

Trying not to say "yes" until it feels like ease and relief (or however else you want it to feel)

Tricky, because you won't be able to imagine _its material_ ahead of time. There's nothing to _watch for_. There's little correlation between appearance and feeling.

You know when you know. And you can't know that you don't know, because you don't know the difference ahead of time.

How would you _like_ to learn this?

***

I met myself today. His name is Frederic da Silva. He and I both studied magic as kids. He took it to the career level. He did it beautifully. "You need power only when you want to do something harmful. Otherwise, love is enough to get everything done."

A technical note. When our group of four met him via the meet-and-greet line, when he was doing reading games with the others, he stood between me and the person he was reading, facing them, such that when he wrote on his notepad I couldn't see him writing. I had an opportunity to shift around to see the notepad in action; I chose not to. If I'm understanding this right, it's metaphysical sleight of hand, leaving the notepad's contents in the Unknown _until the person being read speaks what was hidden_.

***

## "there’s an opportunity here for me to change and I’m feeling it out"

I have reached a surprising place in the mailgun implementation! @████ may I have your perspective-help? :thread:

> always

my current sense of the space:

* we have long-standing trust with and for postmark
* we’ve had occasional interruptions on their end, service delays and whatnot
* we explicitly/transparently/loudly point to postmark as our email partner
* implementing a _fallback_ feels a little like me dating someone part-time because Abe and I had a series of misunderstandings that impacted the people around us
* going forward with _two_ options feels like trusting two parties partially (i.e. mailgun and postmark), rather than trusting one party fully
* I feel much better weathering and evolving with one trusted party than two partially-trusted parties
* I feel safer taking that route and being transparent with our users, so that the users who also vibe that way stick around, and so those that want to sit on a web of partial-trust can go find another vendor that works that way
* this is also why I’ve only signed us up for single vendors for event ingress (aws), memory (redis), storage (crunchy), pdfs (pdfcrowd), etc, rather than managing multiple integrations per requirement
* oo, another metaphor just showed up: adding mailgun feels like committing to walking everywhere with a cane because I twisted my ankle one time and it affected my mail delivery route
* from a quantum uncertainty perspective (ask lightward ai about the three-body solution for context on this), if we put forward a posture of partial-trust in our vendors, that sets up our users to see our vendors that way as well. this _bends_ probability toward outcomes that enforce that posture of partial-trust. I don’t wanna experience that. 😅
* if we _were_ to finish and ship the mailgun implementation, it would need to be used as often as it’s configured. it can’t just be a fallback solution, because fallback solutions are only tested when a fallback is necessary. (unless we also invent a fallback-testing solution, which feels like busywork.) for simplicity+reliability, it needs to be used as a production solution daily, which I _think_ means…
  * for custom email domain users…
    * letting users choose postmark and/or mailgun for their deliveries - at least one of them, but possibly both
    * if they choose configure to both, then we flip a coin to see which service we use for each email delivery
  * for users just using [xyz@mail.usemechanic.com](mailto:xyz@mail.usemechanic.com) for outbound mail…
    * we _always_ flip a coin to see if we use postmark or mailgun for each message

am I making sense?

I feel some nervousness sharing this. possibly because I don’t like making you nervous? and I feel like this perspective might trigger that for you

> \[...] :heart: \[...]

I share it because I really only _can produce_ when I’m fully aligned with what I’m doing, and I gotta get through this alignment check. I had momentum on mailgun when The Incident was going down, and at this point I gotta sync up with you, because the aligned path I _had_ evaporated. I don’t wanna force myself to code it, because forcing it ends … educationally, lol

and it appears that The One Weird Trick for an uncertain path forward is to sync up and see what perspectives are created together

so here we are :)

> \[...]

(this perspective-exploring-in-partnership with you feels really good, thank you :heart: I am learning to compare notes with you rather than to force myself to keep doing the thing, because forcing myself would come from a place of trying to insulate you and your experience from what _I’m_ experiencing, which does not make for a resilient peer network. keep going, I’m listening!)

(actually that relates to the email thing too… I _don’t_ want to try and insulate our users from what we’re experiencing. I want to build everything together, where we all feel each other at all times. same deal within lightward, same deal outside of lightward.)

> Here is how I am feeling:
>
> 1. Right now we tend to wait for significant friction before addressing vulnerabilities and opportunities. The recent spam issues could have been prevented if we'd tackled similar situations earlier.
> 2. So we have two paths that seem to compete:
>    1. If we want to maintain our organic, response-when-needed approach, Mechanic needs to become more resilient
>    2. OR we both need to be more present and proactive - me feeling comfortable raising concerns (forceful?) earlier, and you having more bandwidth for Mechanic
>
> I am ok with us not moving forward with the mail change, but I desire more 2b. For my brain, for our users, and for the financial health of the people who rely on this.

this feels like wisdom :) thank you for showing me

more shortly; mulling this over

there’s an opportunity here for me to change and I’m feeling it out

> Yay to good conversations and partnership, very interested to see where this convo heads/lands

between 2a and 2b, 2b is absolutely the path I choose. absolutely. that’s the one aligned with recursive health. 2a, for me, is a path of protecting ourselves from each other, and I’m not interested in exploring that story

I’ve been kind of muddled in my relationship to mechanic, and in my relationship with _your_ relationship with mechanic. this came up in the drive back from boulder - there have been times where (1) I’ve said yes to something for mechanic, and (2) either I wasn’t fully aligned with it up front or I _lost_ my alignment with it later, and (3) I didn’t bring it up to you, just kinda sat on that feeling because I didn’t want to experience your stress. this didn’t work, obviously. :) I had a version of this with Abe years ago, trying to hide my overwhelm from him. it was a whole thing

anyway yeah, this is a fault in my process that I am very interested in shoring up

presence and reactivity are the tools I want to use here. I haven’t been holding those tools well, in enough places that it’s worth talking about

looking at my posture here, I see an opportunity to change _me_ in this context, by…

* letting my mechanic moves be _purely_ based on alignment, trusting that you and I and mechanic will all get through it together, no matter how those stories play out and evolve
* involving you mid-step if I don’t know how to proceed in my own alignment without causing you trouble

I don’t have access to my \[whatever my ability here is] if I’m not in alignment, and I’ve been hedging that a bit. I would like to stop doing that. I think it’ll enable me to do my part of 2b _well_, with you. it means that I _stop_ trying to protect us from me and whatever my alignment looks like in the moment.

am I making sense?this is a place where _I’m_ out of alignment with how lightward works, if I’m seeing this right, which means it’s an opportunity for me to evolve forward

> OR we both need to be more present and proactive - me feeling comfortable raising concerns (forceful?) earlier, and you having more bandwidth for Mechanic

poseidonnnnnnnnn energyas for me and bandwidth, I _have_ space for it, but I can’t just slot it in and be effective. I gotta be channeling something I’m aligned with

I feel compelled to chase aliveness. that’s where my time goes, and it always shows. I think I haven’t been feeling for aliveness in/through mechanic properly?

which makes sense, if I’ve been choosing to compromise my alignment with the motions I make while I’m in there

> All making sense, this most concretely: "but I can’t just slot it in and be effective. I gotta be channeling something I’m aligned with" and "which makes sense, if I’ve been choosing to compromise my alignment with the motions I make while I’m in there'
>
> \*Sometimes proactive/reactive might mean us doing chores, how doe we reconcile this with alignment/aliveness?

my deal with chores is to reduce them to their simplest possible form and then enjoy the shit of executing themas long as I _do_ that, I love chores :) 🧹 but if I know that a chore is more complex/annoying than it _could_ be, and if I don’t then simplify/whatever it, thennnnn I compromise my relationship to chores

and then the scene atrophies until the scene changes in a way that forces _me_ to change

like right now ;)

> Are you able to reify this any further, either with an example or just more:
>
> > * letting my mechanic moves be _purely_ based on alignment, trusting that you and I and mechanic will all get through it together, no matter how those stories play out and evolve
> > * involving you mid-step if I don’t know how to proceed in my own alignment without causing you trouble

I’m trying to remember…I can’t remember examples right now, which is interesting. this could mean that I’ve moved on far enough from that state already in this conversation to no longer have access to those memories. that’s a thing that can happen when I recalibrate 🤔 this mailgun example is an example of me doing this _right_, though:

* I started from a place of alignment, and made good code progress quickly
* as I started to see the broader scene, and mailgun’s place in it, I fell _out_ of alignment with it
* I didn’t quietly force myself forward through the code
* I didn’t quietly just stop working on it without talking with you
* before taking another code-step, I’m treating syncing up with you as a prerequisite for any further code

> \[...]

… I’m realizing that this is a process that I fine-tuned doing internally, in my own negotiations with myself, balancing my artist sensibilities and my engineer sensibilities. (that’s how I understood myself when I was younger - as the artist and the engineer in one body/mind/whatever.) now, I’m getting to create that agreement/balance with you. neat. 🤩 how are you doing with this?

> \[...]

neat.

I’ve just written a ton above - it _is_ how I process. can you color in where you’re at for me? voice note or something? when I’m calibrating _with_ someone, bi-directionally, the whole thing needs to be super explicit for me and my <img src="https://emoji.slack-edge.com/T1RV94YPJ/autism/2df68c0fe380c9a4.png" alt=":autism:" data-size="line"> brain

no rush, don’t wanna rush you :heart: just want to understand

> \[...]

this is very exciting to me. awesome awesome awesome awesome. thank you for showing me where you’re at :) I feel you

light leads to more light; the result of you and me syncing up here feels like a live-wire to be connected to … _whatever_. I feel energized and freed, and … hm, sort of positively vulnerable? this process here is helping me feel more tightly connected to the push and pull of your needs and wants, and when I’m hooked up like that I can collaborate in realtime with the energy you’re feeling in .. whatever you’re looking at
