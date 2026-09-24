# wangjams.github.io

Source for my personal website, built with Quarto and published with
GitHub Pages at https://wangjams.github.io.
It includes two computational posts analysing the Palmer Penguins data,
one in Python and one in R.

## Requirements

Install these first (versions I used):

- [Quarto](https://quarto.org/docs/get-started/) 1.10.18
- [uv](https://docs.astral.sh/uv/) 0.12.5 (installs Python 3.14.7 for you)
- [R](https://cran.r-project.org/) 4.6.1
- Git

renv (1.2.4) installs itself the first time R starts in this folder.

## Build the site

In a terminal:

```bash
git clone https://github.com/wangjams/wangjams.github.io.git
cd wangjams.github.io
uv sync
```

Then start R in the same folder by typing `R` in the terminal.
In the R console, run:

```r
renv::restore()
q()
```

Answer `y` if `renv::restore()` asks to proceed,
and `n` when `q()` asks to save the workspace.

Back in the terminal, from the top level of the repository:

```bash
uv run quarto render
```

Always run `quarto render` from the top level of the repository,
through `uv run`, so that both the Python and R environments are used.

## Output

The built site is written to `docs/`.
To view it locally, open `docs/index.html` in a browser
(on macOS: `open docs/index.html`),
or run `uv run quarto preview` for a live local server.

## Data

Both posts use the [Palmer Penguins](https://allisonhorst.github.io/palmerpenguins/) data (CC0),
which ships inside the `palmerpenguins` R and Python packages.
It is installed by `uv sync` and `renv::restore()`,
so the build does not download any data from the internet.