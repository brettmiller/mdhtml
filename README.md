# mdhtml

Renders local markdown files as HTML and serves them in your browser. Requires [`uv`](https://docs.astral.sh/uv/).

## Usage

```sh
mdhtml                  # current directory
mdhtml README.md        # single file
mdhtml ~/some/dir       # directory
```

If a single markdown file is found it opens directly. If there are multiple files, an index page is shown with links to each.

The server runs until you press Ctrl-C. Reloading the browser tab re-reads the file from disk, so changes are picked up without restarting.

## Writing to files

Use `-o` / `--output` to write HTML files instead of serving them.

```sh
mdhtml README.md -o             # → README.html (next to the source)
mdhtml README.md -o out/        # → out/README.html
mdhtml README.md -o out.html    # → out.html (exact path)
mdhtml ~/docs -o                # → <file>.html per file + index.html (in source dir)
mdhtml ~/docs -o out/           # → out/<file>.html + out/index.html
```

Output directories are created if they don't exist. When multiple files are written, links in the generated HTML use relative paths so the files work when opened directly from disk.

## Options

| Flag | Description |
|------|-------------|
| `-o, --output [PATH]` | Write HTML files instead of serving. PATH is a directory or (for a single input file) an `.html` filename. Defaults to the source file's directory. |
| `--dark` | Force dark mode |
| `--light` | Force light mode |
| `--theme NAME` | Pygments syntax theme for both light and dark modes (default: `perldoc` / `monokai`) |
| `--list-themes` | Print available theme names and exit |

Without `--dark` or `--light`, the page follows your OS appearance setting. A toggle button in the top-right corner lets you switch modes without reloading.
