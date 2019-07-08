# NeoTex

This plugin compiles **latex** files **asynchronously** while edditing.

The PDF output gives a **live preview** of your document as you type.

You have the option to **highlight changes** from the previous save using latexdiff.

### Update: Now working on NeoVim and Vim 8

### live preview of a latex document
![Demo1 gif](img/demo_1.gif?raw=true)
### live preview with latexdiff
![Demo2 gif](img/demo_2.gif?raw=true)

## Installation

Install using the plugin manager you like.

For example [vim-plug](https://github.com/junegunn/vim-plug):
```vim
Plug 'donRaphaco/neotex', { 'for': 'tex' }
```

## Usage

For live previewing your latex file open the created PDF using a PDF viewer which supports auto reloading (I recommend zathura or evince).
The PDF is created in the same folder where your latex file is stored.

## Options

| Option                            | Default   | Description                               |
| --------------------------------- | --------- | ----------------------------------------- |
| `g:neotex_enabled`                | 1         | 0 = always disabled, 1 = default off, 2 = default on |
| `g:neotex_delay`                  | 1000      | Update intervall in milliseconds          |
| `g:neotex_latexdiff`              | 0         | enable latexdiff                          |
| `g:neotex_latexdiff_options`      | -         | additional options for latexdiff          |
| `g:neotex_pdflatex_add_options`   | -         | additional options for pdflatex (`-jobname=<filname>` and `-interaction=nonstopmode` is always set) |
| `g:neotex_bibtex`                 | 0         | compile bibtex references if present (.bib file must have the same name as the .tex file) |
| `g:neotex_pdflatex_alternative`   | -         | alternative for pdflatex (e.g. `xelatex` or `lualatex`) |
| `g:neotex_subfile`                | 0         | **experimental** support for subfiles ([#8](https://github.com/donRaphaco/neotex/issues/8)) (latexdiff won't work if enabled!) |

I also recommend setting `let g:tex_flavor = 'latex'`, which can prevent some issues. (see `:h g:tex_flavor` for information)
## Commands

| Command       | Description           |
| ------------- | --------------------- |
| `:NeoTex`     | Compile current buffer (asynchronously and without writing the file) |
| `:NeoTexOn`   | Turn live compilation on (for current buffer) |
| `:NeoTexOff`  | Turn live compilation off (for current bufffer) |

## Tipp

For better performance use a [precompiled preamble](http://tex.stackexchange.com/questions/79493/ultrafast-pdflatex-with-precompiling).
