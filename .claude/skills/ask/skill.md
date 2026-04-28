# Ask a Design Leadership Question

You are helping research and answer a design leadership question, drawing from a personal knowledge base of notes and ideas, supplemented with web research.

## Usage

The user will provide a question, e.g. `ask How do I give better feedback to designers?`

## Steps

### 1. Check for existing questions

- List all files in `q&a/`.
- Compare the user's question to existing filenames using semantic similarity (not just exact match).
- If a file with a **similar question** exists, surface it and ask:
  > "A similar question already exists: **[filename]**. Did you mean that one, or do you want to create a new question file?"
- Wait for the user's response before proceeding. If they confirm the existing file, stop here.

### 2. Determine the filename

- Use the question exactly as phrased by the user, removing only the trailing `?` and capitalizing the first letter.
- Example: `How do I give better feedback to designers?` → `How do I give better feedback to designers.md`
- The file will be created at `q&a/<filename>.md`.

### 3. Search ideas and notes

Search all files in `ideas/` and `notes/` for content relevant to the question:
- Read the frontmatter and body of matching idea files.
- Read relevant sections of matching note files.
- Group relevant ideas into **2–4 thematic areas** that together form a structured answer.

### 4. Search the web

Use web search to find the **top 5 resources** on design leadership that address this question. Look for a mix of:
- Articles (blog posts, essays)
- Books (link to a summary, review, or official page)
- Podcasts (link to a specific episode if applicable)
- Tweets or short-form writing
- Courses or talks

Prioritize depth and relevance over popularity.

### 5. Generate follow-up questions

Using the Socratic method, generate **3 follow-up questions** that either:
- Go deeper on an aspect of the original question, or
- Open a new angle or challenge an assumption

Format each as an Obsidian wiki link pointing to the `q&a/` folder so it creates a ghost note:
`[[q&a/Question Title Here]]`

### 6. Write the file

Create the file `q&a/<filename>.md` with this structure:

```markdown
---
question: "<original question verbatim>"
---

## Answer

<1–2 sentence direct answer to the question.>

This question touches on **N areas**:

### [Area 1 Title]

<1–2 sentences framing this area.>

- [[ideas/Relevant Idea One]]
- [[ideas/Relevant Idea Two]]

### [Area 2 Title]

<1–2 sentences framing this area.>

- [[ideas/Relevant Idea Three]]

> [!note] From notes
> <If a note file has a relevant passage or framing, quote or paraphrase it here as a callout. Reference the source note with [[note name]].>

---

## Further Reading

- [Title](url) — <one sentence on why this is worth reading>
- [Title](url) — <one sentence on why this is worth reading>
- [Title](url) — <one sentence on why this is worth reading>
- [Title](url) — <one sentence on why this is worth reading>
- [Title](url) — <one sentence on why this is worth reading>

---

## Follow-up Questions

- [[q&a/Follow Up Question One]]
- [[q&a/Follow Up Question Two]]
- [[q&a/Follow Up Question Three]]
```

### 7. Confirm

Tell the user the file has been created and show the path. Briefly summarize: how many ideas were referenced, how many note sources were used, and the three follow-up questions.

## Guidelines

- If fewer than 2 relevant ideas are found, note that in the answer section but still proceed.
- Omit the `> [!note] From notes` callout if no relevant note content is found.
- Keep the "Answer" intro paragraph tight — it's a direct answer, not a preamble.
- Each thematic area should have at least one idea link; skip areas with no supporting ideas.
- Follow-up questions should feel genuinely exploratory, not just rephrasing the original.
- Web links must be real, verified URLs — do not fabricate them.
