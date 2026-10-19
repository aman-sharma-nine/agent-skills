---
name: vague-topic-to-article-outline
description: Use when the user has a vague topic and wants an outline.
version: 0.1.0
author: Agent Skills Library
license: MIT
platforms: [macos, linux, windows]
metadata:
  hermes:
    tags: [writing, research, substack, outlining, synthesis]
    related_skills: []
---

# Vague Topic to Article Outline Skill

Turn a broad or half-formed topic into a distinctive, researchable article outline without drafting the article for the user. Start from the user's existing work and knowledge base, identify recurring questions in relevant communities, select a focused reader question, and create a section-by-section research scaffold.

## When to Use

Use when the user:
- gives a vague topic and wants help turning it into an article;
- asks for research questions, an outline, or a point of view;
- wants to write manually and have the agent refine the work later;
- asks to connect a new topic to existing wiki pages, projects, or implementation work.

Do not use for:
- writing the finished article immediately;
- generic brainstorming with no research or source work;
- editing an existing draft where the thesis and structure are already clear.

## Core Mental Model

Use this sequence:

```text
Vague topic
  ↓
Existing work and knowledge
  ↓
Recurring external questions
  ↓
Focused reader problem
  ↓
Distinctive thesis
  ↓
Concrete mechanism or design object
  ↓
Section claims and research questions
  ↓
Counterarguments and evidence gaps
  ↓
Reusable outline in the requested workspace
```

The goal is not to predict the future or summarise a field. The goal is to find the strongest intersection between:

1. what the user has actually built, observed, or thought about;
2. what a specific technical reader needs to understand or decide;
3. what current practitioners are actively debating;
4. what can be supported by primary sources and concrete examples.

Use the outlining sequence from [[outlining-an-article|Outlining an Article]]:

```text
topic → braindump → group → shape → one sentence per section → draft
```

For a technical Substack article, add the research layer before drafting:

```text
topic → existing work → recurring questions → focused angle
→ braindump → group → story shape → section claims → research → draft
```

## Procedure

### 1. Define the writing constraint

Before researching, establish:

- intended reader;
- article type: technical essay, field guide, architecture note, contrarian argument, or case study;
- whether the user wants an outline or finished prose;
- where the outline should be saved;
- the user's existing project, implementation, or wiki context.

Default to: technical audience, manual research and drafting, outline only, then later refinement.

Completion check: write one sentence describing the reader and the article's job.

### 2. Inspect the user's existing work first

Read the referenced files completely enough to identify:

- explicit theses;
- concrete journeys or examples;
- architecture boundaries;
- failure cases;
- evaluation criteria;
- trade-offs;
- unresolved questions;
- language the user already uses.

If the user references a wiki or folder, search it for overlapping concepts before inventing a new framing. Read the most relevant concept, source, theme, note, and project pages.

Prefer ideas grounded in the user's own work. A concrete implementation, failed eval, design decision, or unresolved trade-off is usually more valuable than a generic trend claim.

Completion check: list 3–8 reusable principles from the user's material.

### 3. Research recurring practitioner questions

Use web search for current discussions in engineering communities and primary technical sources. Search across several surfaces where appropriate:

- protocol repositories and GitHub issues/discussions;
- official implementation examples;
- engineering blogs and documentation;
- Reddit or other practitioner communities;
- technical forums or conference material.

Search for questions, not just topic names. Examples:

- `[topic] GitHub issue authority`
- `[topic] implementation problem`
- `[topic] engineering discussion failure`
- `[topic] protocol limitations`
- `[topic] production lessons`

Record recurring questions under categories such as:

- identity and authority;
- state and transactions;
- interoperability;
- data and context boundaries;
- safety and abuse;
- evaluation and observability;
- product and operating model.

Do not claim statistical popularity unless a systematic dataset supports it. Use wording such as “recurring questions in the sampled discussions” when the research is qualitative.

Completion check: produce 10–25 recurring questions grouped by theme, with representative sources.

### 4. Select the best article question

Score candidate questions against:

| Test | Question |
|---|---|
| Reader value | Does it help a specific reader make a design or product decision? |
| User authority | Does the user have firsthand work or a developed view here? |
| Evidence | Can the claim be supported by primary sources and examples? |
| Specificity | Is it narrower than the overall topic? |
| Originality | Does it create a point of view rather than a survey? |
| Durability | Will it remain useful after current hype changes? |
| Series potential | Can it lead to follow-up articles? |

Select one main question and, at most, two alternates. Explain why the winner is stronger.

Good question shape:

> How should [specific builder] design [specific system] when [new condition]?

Avoid:

> How will [large technology] change [entire industry]?

Completion check: state the selected reader question and why it wins.

### 5. Derive the thesis from the user's work

Use this template:

```text
The common view is:
The user's work suggests:
That view is incomplete because:
The more useful model is:
The practical consequence for builders is:
The strongest objection is:
```

The thesis should be an arguable claim, not a topic label.

Examples of useful transformations:

- “Agentic ecommerce” → “The merchant agent is a bounded outcome-resolution system, not a chatbot.”
- “Enterprise agents” → “The governed unit is the action system, not the model.”
- “Agent memory” → “Memory is an application-layer control surface, not just a model feature.”

Completion check: write a one-sentence thesis and a 30-second explanation.

### 6. Name or define a concrete mechanism

Give the article a design object that makes the thesis useful. Examples:

- journey contract;
- authority boundary;
- evaluation harness;
- context budget;
- capability surface;
- decision trace;
- outcome ledger;
- intervention loop.

Do not invent jargon merely to sound original. Search whether the term already exists, identify adjacent terminology, and label it as a working term if necessary.

Completion check: define the mechanism in 1–3 sentences and show a small example.

### 7. Shape the article as a story

Do not create a catalogue of topics. Give the reader a reason to continue from one section to the next.

Use this default story flow:

1. **Opening problem or scenario** — show a concrete situation before explaining the topic.
2. **Tension** — reveal why the obvious solution fails or is incomplete.
3. **Thesis** — state the main claim clearly.
4. **Mechanism** — introduce the model, architecture, or design object that explains the problem.
5. **Application** — walk through how the mechanism changes practice.
6. **Guardrails or trade-offs** — show what can go wrong and where boundaries belong.
7. **Evidence and evaluation** — explain how a builder would know the approach works.
8. **Implication** — show what changes for the reader's work or industry.
9. **Open ending** — close with a question or unresolved tension, not a summary.

For every section, write one sentence before writing paragraphs:

```text
Section:
Claim this section makes:
Example or evidence:
Question the reader now has:
How the next section answers it:
```

The next section should usually answer a question created by the previous section. Remove sections that do not advance the story.

Completion check: the outline can be read from top to bottom as a chain of questions and answers, not just a list of themes.

### 8. Braindump, group, and reduce

Before finalising the outline:

1. **Braindump** every relevant idea, example, source, objection, and personal observation.
2. **Search existing material** in the wiki, notes, highlights, and project files.
3. **Group** related ideas and remove material that does not support the selected angle.
4. **Choose a shape** from the story flow above or another appropriate structure.
5. **Write one sentence per section** and check the transitions.
6. **Keep unresolved ideas in a parked list** rather than forcing them into the article.

Do not move directly from topic to prose. The outline is the bridge between raw thinking and the draft.

Completion check: every retained idea belongs to a section, and every section has one main claim.

### 9. Add research questions and evidence gaps

For each retained section, provide:

- research questions the user must answer;
- evidence to find;
- likely counterargument;
- what would change the thesis;
- a concrete example, diagram, or case.

Do not write questions that are merely interesting. Each question must help establish, challenge, or qualify the section's claim.

Completion check: every section has 2–5 answerable research questions and at least one evidence target.

### 10. Add counterarguments and evidence gaps

Do not produce a one-sided trend narrative. Add 4–8 serious objections. For each, create:

```text
Claim:
Evidence for:
Evidence against:
What would change my mind:
Implication for the thesis:
```

Mark claims as fact, forecast, interpretation, or opinion. Identify which claims need primary evidence before publication.

Completion check: list the article's weakest unsupported claim and the source needed to test it.

### 11. Create the outline artifact

If the user asks for a file, create it in the requested location. For Substack drafts, use:

```text
substack/drafts/<descriptive-title>.md
```

Use frontmatter:

```yaml
---
type: substack-draft
created: YYYY-MM-DD
updated: YYYY-MM-DD
status: outline
working_title: "..."
---
```

The file should contain the working thesis, reader, selected question, research discipline, section outline, questions, counterarguments, and source list. Do not write finished article prose unless explicitly requested.

Do not update `wiki/index.md` or `wiki/log.md` for a Substack draft unless the user explicitly asks. Do not modify `raw/`.

Completion check: the file exists, contains the complete outline, and clearly tells the user what to research next.

### 12. Report the result

Give a short report containing:

- the selected framing;
- why it was selected;
- the strongest overlap with the user's existing work;
- where the outline was saved;
- what the user should research and write next;
- any limitation in the research, especially if “most common” was inferred from a qualitative sample.

## Research and Source Discipline

- Use primary technical documentation for protocol and implementation claims.
- Use community discussions to discover questions and failure modes, not as unquestioned evidence of market-wide behaviour.
- Separate protocol capability, implementation behaviour, user trust, and market adoption.
- Prefer concrete examples, traces, eval cases, and failure reports over generic forecasts.
- Cite internet-derived factual claims in the final response when web search was used.
- Do not present qualitative search results as statistically representative.

## Common Failure Modes

- Starting with the industry topic instead of the user's strongest evidence.
- Producing a protocol roundup without an argument.
- Treating an agent as the unit of analysis when the real unit is a journey, workflow, or action system.
- Writing the article before defining the reader's question.
- Confusing a model capability with a production guarantee.
- Treating an API or protocol as proof of safe interoperability.
- Asking research questions that cannot change the article's conclusion.
- Hiding uncertainty behind phrases such as “the market is moving toward”.
- Creating impressive-sounding terminology without checking adjacent literature.
- Drafting polished prose when the user asked to research and write manually.

## Verification Checklist

Before finishing:

- [ ] Existing user files and relevant wiki pages were inspected.
- [ ] The reader and article job are explicit.
- [ ] Recurring community questions were researched and grouped.
- [ ] “Most common” claims are qualified unless systematically measured.
- [ ] One main reader question was selected.
- [ ] The thesis is arguable and grounded in the user's work.
- [ ] A concrete mechanism or design object makes the thesis useful.
- [ ] Every outline section has research questions.
- [ ] Counterarguments and evidence gaps are included.
- [ ] The outline was saved to the requested location.
- [ ] No finished article was written unless explicitly requested.