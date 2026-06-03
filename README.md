# mdhtml

Renders local markdown files as HTML and serves them in your browser. Requires [`uv`](https://docs.astral.sh/uv/).

## Usage

```sh
mdhtml                  # current directory
mdhtml README.md        # single file
mdhtml ~/some/dir       # directory
```

If a single markdown file is found it opens directly. If there are multiple files, an index page is shown with links to each.

The server runs until you press Ctrl-C.

## Options

| Flag | Description |
|------|-------------|
| `--dark` | Force dark mode |
| `--light` | Force light mode |
| `--theme NAME` | Pygments syntax theme for both light and dark modes (default: `perldoc` / `monokai`) |
| `--list-themes` | Print available theme names and exit |

Without `--dark` or `--light`, the page follows your OS appearance setting. A toggle button in the top-right corner lets you switch modes without reloading.
