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

`latexmk` automatically runs LaTeX as many times as needed for generated content such as the table of contents.

In VS Code, install LaTeX Workshop and use the normal build button. The root file selects LaTeX Workshop's built-in `latexmk (lualatex)` recipe, so no repository VS Code settings are needed.

To remove temporary build files while keeping the PDF, run:

```sh
latexmk -c main.tex
```

To remove the PDF and temporary build files, run:

```sh
latexmk -C main.tex
```
