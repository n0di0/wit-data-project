# Women in Technology: Data Portfolio Project Starter

Build something from real data and publish it as a link you can put on your resume or LinkedIn. No experience needed.

## Example projects

See what each track can look like. All four use the Netflix backup data.

- [Dashboard](https://YOURUSERNAME.github.io/YOUR-REPO/examples/dashboard.html)
- [Quiz and Flashcards](https://YOURUSERNAME.github.io/YOUR-REPO/examples/quiz.html)
- [Knowledge Graph](https://YOURUSERNAME.github.io/YOUR-REPO/examples/knowledge-graph.html)
- [Case Study](https://YOURUSERNAME.github.io/YOUR-REPO/examples/case-study.html)

## The steps

1. Pick a topic you're curious about.
2. Find a CSV dataset (see "Finding data" below).
3. Pick a track.
4. Open Google Colab, upload your CSV, and paste your track's prompt into your AI.
5. Download your finished file and upload it to GitHub.
6. Turn on GitHub Pages to get your live link.

---

## Finding data

Look for a CSV with a few hundred rows and a few clear columns. Check the license and credit your source.

- Kaggle: kaggle.com/datasets
- Our World in Data: ourworldindata.org
- data.gov
- Google Dataset Search: datasetsearch.research.google.com
- TidyTuesday: github.com/rfordatascience/tidytuesday
- Wikipedia tables: copy into a spreadsheet, then save as CSV

Stuck? Use the backup dataset: `backup-data/netflix_backup.csv` (450 Netflix movies and TV shows). Details are in `backup-data/DATASET.md`.

---

## Finished examples

Open the files in `examples/` to see what each track can look like. They were all made from the backup Netflix data:

- `examples/dashboard.html`
- `examples/quiz.html`
- `examples/knowledge-graph.html`
- `examples/case-study.html`

To publish yours, the file has to be named `index.html`. These examples keep their longer names so they can sit in one folder.

---

## Using Colab

- Upload a file: run `from google.colab import files; uploaded = files.upload()`
- Download a file: run `files.download("index.html")`
- **Colab erases your files when the tab closes. Download your work before you leave.**

---

## Pick your track and copy the prompt

Before you paste a prompt, replace the parts in [brackets]. Paste your CSV's column names and the first 3 rows into the chat too, so the AI knows what it's working with.

### Track 1: Dashboard (easiest)

```
I'm using Google Colab. I have a CSV file called [filename.csv] about [topic].
Its columns are: [paste column names].

Write Python code that:
1. Loads the CSV with pandas and cleans obvious problems (missing values, wrong types).
2. Makes 3 to 4 Plotly charts that tell a story about [the question I'm curious about].
3. Gives each chart a clear title, labeled axes, and a one-sentence caption.
4. Combines everything into ONE HTML file named index.html, with a page title and a short intro.
   Use include_plotlyjs="cdn" so the file stays small.
5. Ends by downloading index.html with google.colab.files.download.

Keep the code simple and add short comments so a beginner can follow it.
Tell me which question each chart answers.
```

### Track 2: Quiz or Flashcards

```
I'm making a quiz and flashcard website about [topic].

Create ONE self-contained file named index.html with plain HTML, CSS, and JavaScript.
No libraries, no build tools, nothing to install.

Requirements:
- 10 questions about [topic], based on this data: [paste a few rows or key facts].
- A "Flashcards" mode (click a card to flip it) and a "Quiz" mode (multiple choice, instant feedback).
- A score at the end and a "try again" button.
- A clean, modern design using these colors: [your colors].
- Mobile friendly.
- Put the questions in a JavaScript array at the top of the file so I can easily edit them.

Make sure every answer is accurate. If you're not sure about a fact, tell me.
```

### Track 3: Knowledge Graph (most eye-catching)

```
I'm using Google Colab. I have a CSV called [filename.csv] about [topic].
Its columns are: [paste column names].
Column [A] and column [B] should be the connected things
(for example, artist and genre, or actor and movie). Some cells hold several
values separated by commas, so split them and give each value its own node.

Write Python code that:
1. Loads the CSV with pandas.
2. Builds a NetworkX graph where nodes are the values in [A] and [B] and edges connect rows.
3. Keeps the graph readable: limit it to the 50 to 100 most connected nodes, and keep only
   links backed by at least 2 rows of data.
4. Sizes each node by its number of connections.
5. Colors nodes by community using networkx greedy_modularity_communities.
6. Prints the top 5 most connected nodes and one interesting finding about them.
7. Uses pyvis to save an interactive graph as graph.html. Use net.write_html (not net.show),
   Network(cdn_resources="in_line") so the file is one self-contained page, a label font size
   of 18, thin edges, and the pyvis option nodes.scaling.label.drawThreshold = 1 so labels
   show even when the whole graph is zoomed out.
8. Shows the file in Colab with IPython.display.HTML(open("graph.html").read()), and
   downloads it with google.colab.files.download. I will rename it index.html for GitHub Pages.

Keep the code simple and add short comments so a beginner can follow it.
```

**Graph tips**
- If the graph looks like a hairball, lower the node limit or raise the minimum link strength to 3.
- Short on links? Actor-to-title graphs need a big dataset, since most actors appear only once. Genre, country, or category columns link up much more easily.
- If the graph shows blank in Colab, download `graph.html` and open it in your browser. That always works.
- No obvious connections in your data? Ask your AI: "Which two columns could I connect to make an interesting graph?"

### Track 4: Case Study (or your own idea)

```
I'm writing a short data case study for my portfolio.
Topic: [topic]. My CSV is [filename.csv]. Columns: [paste column names].
The question I want to answer: [your question].

Write Python code for Google Colab that:
1. Loads and cleans the data.
2. Makes 3 Plotly charts that help answer my question.
3. Builds ONE HTML file named index.html with these sections:
   Question, Data (where it came from and its license), What I Found (one chart each),
   What I Learned, and What I'd Explore Next.
4. Leaves the "What I Learned" section with a clearly marked placeholder
   so I can write it in my own words.
5. Downloads index.html with google.colab.files.download.

Write a short draft of the "What I Found" text, but keep it plain and specific to the data.
```

**Make it yours:** Case studies are strongest when the opinions are yours. Write the "What I Learned" section yourself.

**Your own idea?** Describe it to your AI the same way: what you have (data, topic), what you want (a page, a tool, a chart), and the format (ONE self-contained `index.html`).

---

## Publish with GitHub Pages

1. Create a new repo on GitHub, for example `my-portfolio-project`.
2. Upload your file. **It must be named `index.html`.**
3. Go to **Settings → Pages**.
4. Under "Build and deployment," choose **Deploy from a branch**, then branch **main** and folder **/ (root)**, then **Save**.
5. Wait a minute or two. Your link will look like `https://yourusername.github.io/my-portfolio-project/`.

---

## Write your project README

Copy this into your project's README.md:

```markdown
# [Project Title]

**Live link:** [your GitHub Pages link]

## What it is
[One or two sentences.]

## The data
Source: [name and link]. License: [license].

## What I made
Track: [Dashboard / Quiz / Knowledge Graph / Case Study]. Tools: [Python, Plotly, etc.]

## What I learned
[One or two things.]
```

Then add the link to your resume or LinkedIn.

---

## When you get stuck

1. Read the error message and paste it into your AI along with the code.
2. Check the starter files in this repo.
3. Ask a neighbor.
4. Ask an organizer.
