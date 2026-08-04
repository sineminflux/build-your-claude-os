# Business Shapes (suggestions, not rules)

The builder proposes a starting set of departments based on how the reader makes money, then the reader adds, removes, and renames them, and locks the result. The shape is a starting point they own, never a fixed template forced on them.

Vocabulary comes from the Front Desk: a **department** is a standing area of the business with a row on the Floor Plan. A **desk** is one named body of work inside a department. The **Shelf** (`00_Shelf/`) is a top-level folder for reference files.

## The root spine (everyone gets this)

Every Claude OS starts with the same top level, whatever the business:

```
CLAUDE.md              the Front Desk (how Claude works in this OS)
MEMORY.md              accumulated facts about the business
memory/                dated session logs
00_Shelf/              reference files, pulled on a trigger
  brand.md             who they are, offers, who they serve, links, channels
  voice-guidelines.md  how they write (produced by the voice builder)
  writing-rules.md     personal banned words and corrections (read by no-ai-slop)
  connections.md       which tools are connected and what for
_outputs/              finished deliverables
```

Then the reader's departments sit at the same top level, each a folder with its own `CLAUDE.md` and `MEMORY.md`, and each with a row on the Floor Plan.

## How to suggest a shape

Ask two or three plain questions first: what the business sells, who it serves, and how work reaches the customer (content, one-to-one delivery, a product, a storefront). Then propose the closest set of departments below and say, in one line, why you picked it. Invite edits before locking.

## Starter department sets

Pick the closest, then customize with the reader. Each becomes a Floor Plan row.

**Creator / audience-led** (newsletter, social, courses)
```
audience/     who they reach and where
content/      ideas, drafts, published pieces (publishing operations live here as desks)
offers/       products, courses, paid things
operations/   admin, money, tools
```

**Coach / consultant** (one-to-one or small-group delivery)
```
marketing/    how people find them
clients/      one desk per client, notes and deliverables
delivery/     methodology, frameworks, session material
operations/   admin, money, tools
```

**Service provider / studio of one** (done-for-you work)
```
marketing/    how people find them
sales/        leads, proposals, pipeline
clients/      one desk per client, projects inside
delivery/     process, templates, past good work
operations/   admin, money, tools
```

**Product / SaaS founder**
```
product/      roadmap, design, releases
marketing/    how people find it
growth/       experiments, funnels, metrics
customers/    support, feedback, research
operations/   admin, money, tools
```

**Ecommerce / physical product**
```
catalog/      products and listings
marketing/    how people find the store
fulfillment/  inventory, shipping, suppliers
customers/    support and reviews
operations/   admin, money, tools
```

**Not sure / mixed** (start minimal and grow)
```
marketing/
delivery/
operations/
```

## Rules of thumb when customizing

- Keep it flat at the top. Departments name the work, not the brand. A named client or a course build is a desk inside a department, not a new top-level folder.
- Fewer departments beat more. Empty folders age badly; add one when there is real work to put in it.
- One business per OS by default. If the reader runs two genuinely separate businesses with different audiences and money, give each its own OS or its own top-level department set. Otherwise keep a single shape and let `brand.md` carry the positioning.
- Every department gets a Floor Plan row, or a future session will never find it.
- Lock the shape only when the reader says it fits. Then scaffold it live: create each department folder with its `CLAUDE.md` and `MEMORY.md`, and write the Floor Plan rows into the root `CLAUDE.md`.
