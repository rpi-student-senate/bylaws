# Senate Bylaws

This repository contains the LaTeX source for the Senate bylaws.

## Getting Started

Clone the repository with its submodules:

```sh
git clone --recurse-submodules <repo-url>
```

If you already cloned the repository without submodules, run:

```sh
git submodule update --init --recursive
```

When updating an existing checkout, use:

```sh
git pull --recurse-submodules
git submodule update --init --recursive
```

The `union-docs-common` directory is a submodule, so it is pinned to the version expected by this repository.

## Building

Install a LaTeX distribution with `latexmk` and LuaLaTeX, then run:

```sh
latexmk main.tex
```

The generated PDF and temporary files are written to `build/`, which is ignored by Git.
This build process works on Windows, macOS, and Linux.

`latexmk` automatically runs LaTeX as many times as needed for generated content such as the table of contents.

Build settings live in `union-docs-common/.latexmkrc`; the root `.latexmkrc` loads that file. GitHub Actions copies `build/main.pdf` to the project root before uploading or committing it.

On pushes to `main`, GitHub Actions commits the updated root `main.pdf` so the repository's history includes the latest document alongside its source.

In VS Code, install LaTeX Workshop and use the normal build button. The root file selects LaTeX Workshop's built-in `latexmk (lualatex)` recipe, so no repository VS Code settings are needed.

To remove temporary build files while keeping the PDF, run:

```sh
latexmk -c main.tex
```

To remove the PDF and temporary files in `build/`, run (the published root `main.pdf` is retained):

```sh
latexmk -C main.tex
```
