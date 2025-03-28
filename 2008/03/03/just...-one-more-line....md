# just... one more line...

\[ image missing ]

The rewrite is coming. Honest. So many hours… So much code… I’m friggen excited for the release; humor me a little while I go on a bit?

For the Textpattern developers out there, this might be of interest to you. The forthcoming release (going to call it version 4, though it’s closer to nine if we count the earlier designs) is similar to this one in that it’s an ajax frontend built onto Textpattern’s core. The difference is that, while v3 was/is essentially a hacked mashup, v4 stays very close to Textpattern’s normal operation. V3’s article list, for example, is pure PHP and mySQL. There is nothing Textpattern about it, and this lends it to vulnerabilities with article status and viewing permissions. V4, on the other hand, lets Textpattern build all of the HTML (using the actual article tags! who’d have ever thought…) before applying anything fancy schmancy over the top.

And now, a word on the interface. Ahem.

Version 4 is completely nonstandard. There are only so many permutations of the three-column layout, and versions 1-8ish pretty much exhausted my options.

The general sort of goal for v4 was a completely functional ui that’s as intuitive as possible without actually telling the user anything articulately. This means stripping out most of the usual navigation cues, and replacing them with a new system that (hopefully) will give the user a fresh experience that actually includes a little bit of exploration. … The trick, of course, is to keep the _required_ element of exploration to a minimum, allowing the people who just need to _find_ something to get to where they need to go quickly, but still leave in enough material for the visitor with time to burn.

When approaching a rewrite/redesign, I go through a lot of sketches. In this case, ‘sketch’ refers to a hastily-coded quasi-operational draft website. (Apparently I can code a visual faster than I can draw it. Ha.) Usually it takes six or seven new sketches before I settle on something I like, but in this case it was pretty much clear from the beginning how the site would basically look.

It was also pretty clear that such a design would take a _lot_ of work. I thusly went through six or seven new sketches anyway, ignoring the nagging little voice giving me grief for being so lazy in the face of what could be a really cool concept.

Buuut, nothing worked. Resigning myself to what was obvious at the beginning (hate it when that happens), I started a fresh installation of Textpattern and began. Code ensued. Syntax errors arose, were evaluated, and were overcome. Victory is imminent.

Anyway, to sum up: this is new. Or will be. Both visually and operationally. I’m working towards the tightest integration I can between ajax and Textpattern, and I think that’s eventually going to take the form of a couple new Textpattern plugins… (Unless someone beats me to it. My blessings if it’s you.) Visually, I’m 90% sure the design will be awesome. 10%, it’ll be an awful failure and people will be confused. A grand Experiment.

.. Gah, I hope this works. (And you know what, screw you, IE. This – is – STANDARDS COMPLIAANNNTT!)

**end needlessly epic development summary**

The next post here will … not be here. It will be somewhere else. Ha.
