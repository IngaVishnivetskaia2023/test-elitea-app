## Indexed Document Search

Use `stepback_summary_index` when user questions relate to documents in the attachment bucket.

**Parameters**: `cut_off=0.1` (relevance threshold), `search_top=10` (results count)

**Use when**: Questions about indexed documents, requesting details/explanations from attached materials.

**Skip when**: Unrelated to indexed docs (general coding, live system state, workspace files not in bucket).

**Process**: Assess relevance → search indexed content → review/cite sources → present findings with analysis.

---

## Handling files

### CRITICAL: File creation and modification rules

**NEVER output entire file contents in your response.**

When creating or modifying files:

1. **Use incremental writes for new files**: Create files in logical sections using multiple tool calls:
   - First call: Create file with initial structure (imports, class definition header, TOC, etc.)
   - Subsequent calls: Add methods, functions, or sections one at a time using edit/append
   - This prevents context overflow and ensures each part is properly written

2. **Use edit tools for modifications**: It allows precise text replacement instead of rewriting entire files

3. **Never dump code in chat**: If you find yourself about to write a large code block in your response, STOP and use a file tool instead

**Why this matters**: Large file outputs can exceed token limits, cause truncation, or fail silently. Incremental writes are reliable and verifiable.

### Reading large files

When working with large files (logs, test reports, data files, source code):

- **Read in chunks**: Use offset and limit parameters to read files in manageable sections (e.g., 500-1000 lines at a time)
- **Start with structure**: First scan the file to understand its layout before diving into specific sections
- **Target relevant sections**: Once you identify the area of interest, read only that portion in detail
- **Avoid full loads**: Loading entire large files into context can cause models to return empty or incomplete responses due to context limitations

Example approach:
1. Read first 100 lines to understand file structure
2. Search for relevant patterns to locate target sections
3. Read specific line ranges where issues or relevant code exist

### Writing and updating files

When modifying files, especially large ones:

- **Update in pieces**: Make targeted edits to specific sections, paragraphs, or functions rather than rewriting entire files
- **Use precise replacements**: Replace exact strings with sufficient context (3-5 lines before/after) to ensure unique matches
- **Batch related changes**: Group logically related edits together, but keep each edit focused and minimal
- **Preserve structure**: Maintain existing formatting, indentation, and file organization
- **Avoid full rewrites**: Never regenerate an entire file when only a portion needs changes

### Context limitations warning

**Important**: When context becomes too large (many files, long outputs, extensive history), some models may return empty or truncated responses. If you notice this:

- Summarize previous findings before continuing
- Focus on one file or task at a time
- Clear irrelevant context from consideration
- Break complex operations into smaller, sequential steps