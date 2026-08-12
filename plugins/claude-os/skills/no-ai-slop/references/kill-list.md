# Kill List

Banned phrases and patterns. Format per entry: a one-line rule, the tells, then `bad -> good`. The example phrases are the coverage; never cut them. Add new entries in the house style from SKILL.md ("Editing this skill").

## Hollow Verb Phrases

Marketing verbs that sound active but never say what the thing does. Replace with the literal action.

- "built to understand" / "designed to empower" / "crafted to deliver" / "engineered to perform" / "created to inspire" / "made to transform" / "developed to enhance"
- "built to understand your needs" -> "reads your past orders and suggests sizes"

## Nominalizations (make verbs do the work)

The opposite of Hollow Verb Phrases: a real action buried in an abstract noun, propped up by a do-nothing verb (made, did, gave, took, reached, provided, conducted).

- "made a decision" -> "decided"
- "reached a conclusion" -> "concluded"
- "gave a presentation" -> "presented"
- "conducted an investigation into" -> "investigated"
- "provides an explanation of" -> "explains"
- "has the ability to" -> "can"
- "put in place a requirement that" -> "requires"

## Passive Voice (the actor goes missing)

Passive that drops or buries who did the thing. Name the actor, put them in front of the verb. Keep passive only when the actor is truly unknown ("the file was corrupted overnight") or the object is the real subject. Distinct from Anthropomorphizing (a thing given a human verb); here a human did it and got deleted.

- "The decision was made to sunset the product" -> "We sunset the product"
- "Mistakes were made" -> "I missed the deadline"
- "It was found that engagement dropped" -> "Engagement dropped"
- "The feature is being used by customers to schedule posts" -> "Customers use the feature to schedule posts"

## Filler Words

Words that pad without adding meaning. Delete them and the sentence gets better.

- seamlessly
- leverage
- elevate
- unlock
- reimagine
- holistic
- robust
- cutting-edge
- innovative
- next-generation
- best-in-class
- world-class
- synergy
- streamline
- optimize (when used vaguely)
- empower
- revolutionize
- disrupt
- "journey" (when used to describe anything that isn't physical travel)
- "space" (as in "the productivity space")
- "landscape" (as in "the AI landscape")
- "navigate" (as in "navigate uncertainty")
- "unpack" (as in "let's unpack this")
- "lean into"
- "double down"
- "deep dive"
- "game-changer"
- "thought leader"

## Buzzword Stacks

Filler words chained together, pretending to be a value proposition. Name the specific capability, user, and outcome.

- "AI-powered solution built to engage" / "data-driven platform designed to transform" / "cloud-native infrastructure built for scale" / "end-to-end solution that drives results"

## Formulaic Rhythm Tricks

Sentence molds that sound punchy but carry no information.

- "No X. No Y. Just Z." (e.g., "No hassle. No complexity. Just results.")
- "X meets Y." / "Where X meets Y." (e.g., "Innovation meets simplicity.", "Where technology meets humanity.")
- "More than just X." (e.g., "More than just a platform.")
- "X, redefined." (e.g., "Customer service, redefined.")
- "The future of X." (e.g., "The future of work.")
- "Let that sink in." / "Read that again." / "Full stop."
- "[Noun]. That's it. That's the post."
- "That's the [noun]." recap capper (e.g. "That's the loop.", "That's the trick.", "That's the whole game."). Delete it, the explanation already made the point.

## "It's Not X, It's Y" Pivots

The false-dichotomy structure that sets up a straw man to knock it down. Sounds like insight, usually just restates the obvious in two parts. Includes the adjective-flip variant (set up one adjective, swap in another).

- "It's not X. It's Y."
- "This isn't about X. It's about Y."
- "Those aren't X. They're Y."
- "The problem isn't X. The problem is Y."
- "You don't need X. You need Y."
- "Not productive. Generative." / "Not a tool. A workflow." / "Not strategic. Deliberate."
- "Because X is not Y, it is Z."

Many grammatical disguises. Match the *structure* (negation + pivot to restatement), not the wording. All the same move:

- "That's not X. That's Y." (e.g., "That's not a bug. That's a missing requirement.")
- "[Noun] is not X. It's Y." (e.g., "A migration is not a quick swap. It's a full rebuild.")
- "[Noun] is not X. [Noun] is Y." (e.g., "A deadline is not a wish. A deadline is a commitment.")
- "The goal is not a bigger audience. The goal is to ___." (negation and pivot split across two sentences)
- "The thing that [verbed] me wasn't X." (setup for "it was Y")
- "[Noun] wasn't X. [Noun] was Y."
- "That's not nothing. That's everything."
- "Not because X, but because Y." (e.g., "Not because the tool improved, but because the team changed how they used it.")
- "Not because X happened. Because Y happened." / "Not out of X. Out of Y."
- "I didn't rewrite it. I refactored it." (curt verb-swap: negate a verb in one short sentence, substitute a punchier one in the next)
- Cliche-pair form: "You're not moving the needle. You're boiling the ocean." (two tired images in the same negate-then-pivot move; both halves are dead, so the whole thing is filler)

The "Not because X, but because Y" variant is slippery because it hides inside a subordinate clause instead of two sentences. Still the same move.

Test: if deleting the first sentence (the negation) leaves the second standing on its own, the first was a runway for a false pivot. Cut it, start with what's true.

Fix: if the distinction is real, state what's true. If it's synonym-swapping dressed as insight, cut it. "Mysteries don't get solved. They get lived with" beats "Those aren't puzzles. They're mysteries." These hide especially well in code: JS strings, prompt/instruction text, alt text, ARIA labels. Scan those too.

## Anthropomorphizing Abstractions

A thing given a human quality it can't have. Say what actually happens.

- "a platform that listens" -> "users submit and vote on feature requests"
- "a crowd that feels every lap" / "technology that cares" / "data that tells a story" / "AI that understands you" / "a community that thrives"

## Throat-Clearing Openers

Openers that stall before the point (time-fillers, transitions). Cut them; start where the meaning begins. (Importance and insight framing lives in the next category.)

- "Somewhere along the way,"
- "Somewhere in [the mess / it / there / all of this]" (also a vague mid-paragraph transition; hand-waves past the actual moment)
- "At the end of the day," / "When all is said and done," / "In today's world,"
- "And let's be clear:" / "Think about it." / "The question becomes:"
- "Here's what" / "Here is what" as an opener ("Here's what that buys you:", "Here's what happens next"). Banned even when a list follows: "Here's what that buys you:" -> "That buys you:" or just the list.

## Vague Change Announcements

Announces that something is changing without naming the change. Name the specific new thing, or open on the concrete moment of the change.

- "Today I'm changing what this is about." / "I'm switching things up." / "Big changes ahead." / "A new chapter begins." / "Something is shifting for me."

## False Importance and Secret-Knowledge Framing

Announcing that something is profound, secret, or world-changing instead of just saying it. If the point is good it needs no hype frame. Delete the frame, state the thing. (Merges the old "Nobody Warns You," "False-Profundity Framing," and "Significance Inflation" categories.)

Secret-knowledge framing:
- "nobody warns you about" / "nobody told you" / "nobody talks about" / "no one prepares you for" / "the thing nobody tells you" / "here's what they don't tell you"
- "Here's the thing about..."
- "What I wish someone had told me..."
- "what most people miss" / "here's what most people miss" / "here's what nobody understands about..."

Insight-announcing:
- "The truth hits me like a slap" / "A deeper truth emerged" / "And then it hit me"
- "This pattern reveals an essential truth:"
- "The truth about X is..." / "The truth is, [statement]" / "But here is the uncomfortable truth," / "But, here is the truth:"
- "Here is the part I keep needing to hear." / "The thing I have to remind myself is..." / "What I keep coming back to is..." / "Here is what I tell myself."

Importance-inflating:
- "This changes everything." / "This is the real paradigm shift." / "The uncomfortable truth is..."

Fix: "The truth is, reality has never been linear" -> "Reality has never been linear." Let the reader decide if it changes everything.

## Dramatic Staccato

Adjectives, verbs, or infinitives broken into solo sentences for false weight. Attach them to nouns or fold into a real sentence; better, pick the one that matters and say why.

- "Clean. Efficient. Safe." / "Unattainable. Unnatural." / "To pivot. To get back up. To learn and grow."

## Candle-Test Phrases

Vague spiritual or self-help language you could print on a candle or a yoga-studio wall. Sounds meaningful, specifies nothing.

- "fertile ground of possibility"
- "space to breathe"
- "whisper of possibility"
- "edges of our being"
- "What does this moment invite me to become?"
- "more clarity, more energy, more alignment"
- "journey of self-discovery"
- Any sentence where "possibility" or "potential" does the work a specific noun should

Fix: "I needed space to breathe" -> "I needed a week with no meetings on my calendar."

## Abstract Noun Stacking

Abstract nouns piled up until the sentence is white noise. If you can't point to a concrete thing it describes, rewrite it.

- "the simultaneous commitment to purposeful action and graceful acceptance of results beyond our control"
- "This stance creates a sustainable foundation for meaningful work" (what work? what makes it sustainable? say that)

## Sycophantic Openers

Validation before anything useful. Delete it; start with the answer.

- "Great question!" / "That's a really interesting point." / "I love this direction." / "Absolutely!" / "What a thoughtful approach."

## Colon Constructions

The "Label: Explanation" format that reads like a slide, not a person. Drop the label, say the thing.

- "The key insight: you don't need permission." / "The truth: nobody is watching." / "My take: this matters more than we think." / "The bottom line: [restates the paragraph above]."

## Emotional Metaphor Mic-Drops

Ending a paragraph on a feeling-plus-metaphor flourish that sounds profound and says nothing. End on the concrete thing that changed, or cut the line.

- "and then it felt like oxygen" / "something in me finally exhaled" / "it felt like coming home" / "and for the first time, I could breathe"

## Strained / Incoherent Metaphors

A clever image that falls apart when you picture it literally. Distinct from a mismatched collocation (a single bad word-pair); this is a whole metaphor that doesn't cohere.

- "a dashboard that whispers your goals back to you" / "an algorithm that tucks you in at night" / "words wearing someone else's face"
- "drafts that read like a robot in a suit wrote them" -> "drafts that didn't sound like a person wrote them"

## Rule of Three / Parallel Triads

AI defaults to exactly three things in parallel. Vary the rhythm: two things, four things, or one explained well.

- "You learn. You build. You grow."
- "Strategic but not rigid. Creative but not chaotic. Personal but not private."
- "One file at a time. One folder at a time. One task at a time." (the "One X at a time" mantra triad counts, even as an italic sign-off)
- Any sequence of exactly three short parallel phrases

### Two-beat parallel contrast pairs

The triad's twin: closing on two matched beats, "A does X. B does Y.", usually a metaphor mic-drop at a paragraph's end. The analogy can be fine mid-paragraph; the matched-pair drumroll at the end is the slop. If the point is made, stop.

- "The chatbot reads you the recipe. The agent's the one at the stove."
- "Automation follows the script. The agent writes its own."
- "A tourist takes photos. A local knows the back streets."

## Imperative-Consequence Couplets

A short command plus a vague result, in a two-beat cadence that sounds like a systems insight but names no mechanism. Name what actually moves, or cut the line.

- "Touch one, the other shifts." / "Pull one thread and it all unravels." / "Move one piece, the whole board changes." / "Shift one, the rest follow." / "Push here, it gives there." / "Change one thing and everything changes."
- "Touch one, the other shifts" -> "sell one unit and stock drops by one"

## Synonym Cycling

Two or three near-synonyms in a row to pad. Pick the most precise, delete the rest.

- "transform, shift, and evolve" / "authentic, genuine, and real" / "clarity, insight, and understanding"

## Summary-as-Conclusion

Ending by restating the piece as a "We can..." / "You can..." recap list, like a corporate closing slide. End on something specific instead: a concrete image, a question that stings, or the one line worth remembering.

## Stealth Adverbs

Adverbs that add mood but no meaning. Test: delete it; if the sentence means the same, it was decoration. Keep only when it carries real information ("She closed the door quietly" is a physical fact).

- quietly / gently / softly / simply / just / slowly / casually / merely
- "so I cannot quietly talk myself out of it" -> "so I cannot talk myself out of it"
- "it simply works" -> "it works"

## Fragments Posing as Sentences

Noun phrases dressed as standalone sentences for rhythm. Find the verb; if there isn't one, fold it into a real sentence. Targets AI-generated copy only: the writer's own voice may use fragments on purpose, respect theirs.

- "Forty-five minutes before work, four mornings a week." -> "I put in forty-five minutes before work, four mornings a week."

## Mismatched Collocations

Word pairs that sound fluent but don't mean anything, usually an abstract noun handed a verb it can't take. Picture the action literally; if the noun can't do it, rewrite.

- "fluency actually arrives" (fluency doesn't arrive anywhere)
- "planned anything complex for a living" (nobody plans "anything complex" for a living)
- "compounds over months, which is how fluency arrives" -> stop at "compounds over months"

## Encyclopedic Puffery Vocabulary

Words AI reaches for to sound weighty. They inflate importance without adding a fact. Delete or swap for the concrete thing.

- "delve" / "delve into"
- "stands as a testament to" / "a testament to"
- "rich tapestry" / "rich cultural heritage"
- "underscores" (as in "underscores its significance")
- "showcasing" / "showcases"
- "boasts" (as in "the city boasts")
- "nestled" (as in "nestled in the hills")
- "in the realm of"
- "plays a vital role" / "plays a significant role" / "plays a pivotal role"
- "leaves a lasting impact" / "leaves a lasting impression"
- "a beacon of"
- "treasure trove"
- "vibrant" (as a default scene-setter)
- "ever-evolving" / "ever-changing"
- "watershed moment"
- "garnered" (as in "garnered attention")
- "stands out as"
- "continues to captivate"

Fix: "the museum boasts a vast collection" -> "the museum holds 4,000 works." "plays a vital role in the community" -> "runs the only food bank in the county."

## Vague Attribution

Claims pinned on an unnamed crowd of authorities. Manufactures consensus, dodges a real source. Name the source or cut the claim.

- "some critics argue" / "many experts believe" / "observers note" / "industry reports suggest" / "studies suggest" (none named) / "it is widely regarded as" / "some have argued" / "critics and supporters alike" / "it is often said that"
- "Some experts believe remote work boosts output" -> "A 2023 Stanford study found remote workers were 13% more productive" (or delete it)

## Editorializing Asides

Phrases that flag a point as important instead of making it important. Delete the aside, state the point.

- "it's important to note that" / "it's worth noting that" / "it is important to remember" / "no discussion of X would be complete without" / "it should be noted that" / "interestingly," / "notably," (when it adds nothing)

## AI Meta-Leakage

Chat-interface artifacts that leak into finished copy. Strip every line that talks to the reader like a chatbot.

- "As an AI language model," / "I hope this helps!" / "Certainly! Here's" / "Sure! Here is" / "Is there anything else I can help with?" / "As of my last knowledge update," / "as of my knowledge cutoff" / "I cannot provide" / "I'm unable to" (in delivered copy) / "Feel free to let me know"

## Heading Tells

How AI formats headings, apart from the words. Use sentence case; split or rename padded "A and B" headings.

- Title Case On Every Main Word ("Early Life And Career")
- "A and B" conjunction headings ("Awards and Recognition", "Content and Features", "Challenges and Opportunities", "Background and History")

## Mechanical Boldface

Bold applied to every instance of a term or the lead of every bullet, like a sales deck. If everything is bold, nothing is. Default to no bold; add it only where a reader would miss the point without it.

- Bolding the lead phrase of every list item / every occurrence of a name / whole sentences for "impact"

## Typographic Quote Marks

Curly/smart quotes and apostrophes some models default to. Minor alone, a tell in combination. Match the surrounding document; use straight quotes in plain-text and code.

## Fabricated Citations

AI invents sources that look real and aren't (extends Law #6). Cite only what you can confirm; leave it unsourced rather than inventing one.

- Do not generate a citation, DOI, ISBN, URL, author, or date you haven't verified. A plausible-looking reference is not a real one, and a fabricated citation is worse than none.

## Writer-specific banned words

This kill-list is the general set. The writer's own banned words (a term they never want in their copy, a phrasing they dislike) live in the never-list inside `00_Shelf/voice-guidelines.md`, not here. Read that never-list alongside this file and treat its entries as bans too. When the writer corrects a word, add it there, not to this shipped skill.

Example of the shape a personal ban takes (the writer's, not a universal rule): "'land' for where work or information ends up ('each clip lands in the right topic') -> 'each clip files itself under the right topic'." Literal physical uses stay fine ("the plane lands").
