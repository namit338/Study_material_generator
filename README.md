I built this during exam season because I was tired of manually making notes from 80-slide lecture PDFs the night before an exam. The idea was simple — upload your file, and get exam-ready material out. No paraphrasing random internet stuff, just your own syllabus turned into something actually useful.
What it does
Upload a PDF or PPT and StudyForge generates:

Concise notes — the important stuff, trimmed down
Key concepts — terms and ideas worth remembering
Practice quiz — MCQs to test yourself
Long 5-mark Q&As — formatted for university exam answers

All four outputs in one click.
How it works
The whole thing runs in the browser — no backend, no server. When you upload a file, pdf.js extracts the text client-side. That text gets sent to the Anthropic Claude API with structured prompts I wrote to generate each type of output in JSON format, which the app then renders dynamically.
You bring your own Anthropic API key (free tier works). The key never touches any server of mine — it goes directly from your browser to Anthropic. No accounts, no data stored anywhere.
Tech used

Vanilla JS + HTML/CSS (no frameworks)
pdf.js for client-side document parsing
Anthropic Claude API for generation
Prompt engineering with JSON-structured outputs
Deployed on GitHub Pages

Why I built it this way
I specifically didn't want a backend because I didn't want to deal with storing user files or API keys. Keeping everything client-side was a deliberate choice — it's simpler, cheaper to host (free), and honestly more private for the user.
The hardest part was getting the prompts right. Getting Claude to consistently return well-structured JSON for all four output types without breaking the rendering took a lot of iteration.
