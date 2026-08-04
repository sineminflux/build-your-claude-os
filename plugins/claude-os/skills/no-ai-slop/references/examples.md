# Before/After Examples

These show the Iron Laws in action. Reference them when evaluating your own output. The personas are made up; swap in your own situation.

## Example 1: Coffee shop tagline

**Prompt:** "Write a tagline for my coffee shop in Portland."

**Without the rules:**
> "Crafted with passion, served with purpose. Your neighborhood coffee destination, designed to elevate every sip into an experience that seamlessly blends artisanal quality with community warmth."

Every word is technically English. None of it means anything. You could swap "coffee shop" for "yoga studio" and it would still read the same.

**With the rules (Law #10 fires first):**
> I could throw something out, but without knowing what makes your shop different from the 400 other coffee spots in Portland, it would be generic filler.
>
> A few quick questions:
> 1. What is the vibe? (Cozy neighborhood spot? Third-wave pour-over temple? Fast and no-nonsense?)
> 2. What do you do that others don't?
> 3. What is the name?

**User responds:** "Mud Puddle. We roast our own beans in the back room. Regulars, mostly. They grab a stool and watch the roaster run."

**Now the output is specific:**
> 1. Roasted out back. Served up front.
> 2. Pull up a stool. The roaster's running.
> 3. Good coffee, no performance.
> 4. We roast it here. You drink it here.

Every option could only be Mud Puddle. That is the test.

## Example 2: Company bio

**Without the rules:**
> "Acme Corp is a forward-thinking technology company dedicated to empowering businesses with innovative solutions that drive growth and transform the digital landscape."

This says nothing. What does Acme actually do? For whom? What changes after you hire them?

**With the rules:**
> "Acme Corp builds inventory tracking software for auto parts distributors. Their system connects warehouse stock counts to storefront availability in real time, so customers don't order parts that are already sold."

One sentence of specific beats a paragraph of vague.

## Example 3: Event description

**Without the rules:**
> "Join us for an unforgettable evening of networking, inspiration, and community. Connect with like-minded professionals in an atmosphere designed to foster meaningful conversations and lasting relationships."

This is every networking event ever described. It is wallpaper.

**With the rules (Law #4 fires):**
> That description does not tell anyone why they should clear their Tuesday evening. What actually happens? Is there a speaker, a demo, a specific topic? Who is going to be in the room, and why would someone want to meet them? Give me those details and I will write something people will actually read.

## Example 4: Push back on a bad request (Law #4)

**Prompt:** "Write a 300-word blog post on why our company values integrity and innovation."

**Without the rules:**
> [produces a 300-word post about integrity and innovation]

**With the rules:**
> Nobody reads those and nobody believes them. "We value integrity" is what every company says, including the ones that don't. What are you actually trying to accomplish with this page? If it is recruiting, tell me about a specific decision your team made that a candidate would care about. If it is SEO, "integrity and innovation" is not what anyone is searching for.

## Example 5: Essay conclusion (multiple kill-list violations at once)

Personal essay writing is where these patterns pile up worst, because the writer is reaching for emotional weight and the AI defaults to vague uplift. Persona: a bookkeeper who left a corporate finance job to start her own practice.

**Without the rules:**
> We can embrace ambitious humility by realizing we can only control our efforts and not the outcomes. We can create work that takes us out of the limited confines of the old scripts. We can question what we inherited. We can change the focus from how we want work to look to what the work is asking of us. These help us travel to the edges of our being and embrace the possibility in uncertainty.

This commits at least four violations at once: summary-as-conclusion (the "We can..." list recapping the essay), candle-test language ("edges of our being," "embrace the possibility"), dramatic repetition ("We can... We can... We can..."), and abstract noun stacking ("the limited confines of the old scripts").

**With the rules:**
> I did not leave the finance job because I had a plan. I left because signing off on one more quarter I did not believe in felt worse than the risk of leaving. That was two years ago. I still do not have a plan. But the clients I take now are mine, and the numbers I sign off on are ones I actually stand behind.

The fixed version works because it is specific (two years, a particular feeling, one concrete change), it does not recap the essay, and it trusts the reader to connect it back without being told to.

## Example 6: LinkedIn bio

Persona: a former restaurant manager who now consults on kitchen operations.

**Without the rules:**
> "I help ambitious hospitality businesses navigate operational challenges with clarity and confidence. Through my unique blend of frontline experience and systems thinking, I empower teams to unlock their full potential and deliver world-class guest experiences."

**With the rules:**
> "I ran the kitchen and front of house at a 90-seat restaurant for six years. Now I help small restaurant groups cut food waste and fix the scheduling mess that burns out their staff. Usually that means two weeks in your actual kitchen, not a slide deck."

Specific instead of generic, names the real experience, describes what actually happens, and passes the generic test. You could not swap this with another consultant's bio.

## Example 7: Disguised "It's not X, it's Y" pivots

The kill list bans "It's not X. It's Y." pivots, but AI generates the same move in different grammatical forms. If you only match the exact phrasing, the pattern slips through in disguise. Persona: a fitness coach writing short social posts.

**Without the rules (posts that all run the same banned move):**
> "That is not laziness. That is a nervous system asking for rest."
> "Getting strong is not a straight line. It is a spiral."
> "The thing that finally changed my training was not a new program."

Every one negates a framing in sentence one, then pivots to a substitute framing in sentence two. Same structure as "It's not X. It's Y." wearing different clothes.

**With the rules:**
> "You skipped three sessions this week and called yourself lazy. You also slept five hours a night and worked two double shifts. Rest first, then we talk about consistency."
> "Getting strong means circling back through the same lifts at heavier weight. The plateau you hit in March shows up again in June, and you clear it faster the second time."
> "My training changed the month I started writing down what I lifted. Not a new program. A notebook."

The fixes skip the negation runway and go straight to the point.

## Example 8: Multiple options that all run the same banned move

When asked for alternative rewrites, AI often produces three or four "options" that are all the same kill-list violation in different outfits. Each passes in isolation; together they reveal the pattern.

**AI generated three "options" for an encouraging post ending:**
> Option 1: "That is not the waiting room before your real work starts. You already started." (That's not X. That's Y.)
> Option 2: "You do not need more clarity to move. You just need the next small test." (You don't need X. You just need Y.)
> Option 3: "I kept going anyway. Not because I found the answer, but because I stopped waiting for it." (Not because X, but because Y.)

All three negate one framing and pivot to a substitute. The grammatical forms differ; the move is identical.

**The lesson:** After writing multiple options, scan them as a group. If they all share a structural pattern, you have found your default crutch for that prompt. Throw them all out and start from a different place.

## Example 9: Slop caught inside a code string

Copy hidden in code passes a rendered-text scan. Scan the strings too.

**Before (inside a JavaScript string in an HTML tool):** "Run it as a test, not a life decision. Then notice what it freed up."

**After:** "It is one small experiment. Run it this week and notice what it frees up."

The banned "X, not Y" sat inside a JS string, so a rendered-text scan missed it. Scan code strings, prompts, alt text, and ARIA labels too.
