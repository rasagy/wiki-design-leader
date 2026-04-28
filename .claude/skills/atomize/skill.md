# Atomize Notes into Ideas

You are helping extract atomic, Zettelkasten-style ideas from a note file.

## Usage

The user will either:
- Provide a filename or path (e.g. `atomize Design Leadership Handbook`)
- Be working in a notes file in the IDE

If no file is specified, ask the user which file in `notes/` to atomize.

## Steps

1. **Locate the source file** in the `notes/` folder. Match partial names if needed.

2. **Read the full file** carefully.

3. **Extract atomic ideas**: Identify every self-contained, standalone concept — a principle, insight, framework, distinction, or piece of advice. Each idea should be:
   - Understandable without the surrounding context
   - About a single thing (not a cluster of related points)
   - Genuinely interesting or useful on its own

4. **For each idea**, create a file in `ideas/` with:

   **Filename**: A succinct phrase in less than 10 words, written in Title Case, with spaces (not hyphens). Example: `Hunters and Farmers Designer Archetypes.md`

   **Content structure**:
   ```
   ---
   source: "[[NOTE NAME WITHOUT .md EXTENSION]]"
   chapter: "Chapter N: Chapter Title"
   ---

   One to three sentences explaining the idea clearly and self-sufficiently.
   If the original note has a relevant quote, include it as a blockquote.
   ```

   For `chapter`, use the chapter number and title exactly as they appear in the source note (e.g. `"Chapter 3: Managing a Design Team"`). If the idea comes from introductory, cross-cutting, or non-chapter content, use `"Introduction"` or `"Cross-Cutting Themes"` as appropriate.

5. **Create the `ideas/` folder** if it does not exist.

6. **After creating all files**, summarize: how many ideas were extracted, and list the filenames created.

## Guidelines

- Prefer more, smaller ideas over fewer, larger ones
- Don't just copy bullet points verbatim — restate the idea in a complete, standalone sentence
- The body should make sense to someone who hasn't read the source
- Skip purely structural content (chapter intros, summaries of summaries)
- If two bullet points express the same idea, merge them into one atomic note
