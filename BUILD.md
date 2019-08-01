# Overview

This file documents the steps to build the VRKB manual: `README.md`.

Provided all the dependencies are correctly installed (see below), you should be able to run

    `./build <VRKB_Unity_dir>`
	
to build an up-to-date version of `README.md` and `doxygen-html`.

# Dependencies

- `doxygen`, for extracting documentation from the XML code comments
- `jq`: JSON query tool
  - install `jq` with `apt-get install jq`
- `yq`: provides an `yq`/`xq` scripts that can query YAML/XML documents using the same syntax as `jq` (`yq` is a similar wrapper for YAML files)
  - I use `xq` for extracting strings from the doxygen-generated XML files
  - install the `yq` package with `pip3 install yq`
- `m4`, for assembling the various pieces of text into a single document (in `build.sh`)
  - install with `apt-get install m4`
- `markdown-toc`: https://github.com/jonschlinkert/markdown-toc, for auto-generating a table of contents for the document
  - I had to install `npm` (Node Package Manager) for this
  - I also needed to set up some environment variables in my `$HOME/.profile`, so that `npm install -g markdown-toc` would install to my `$HOME/.npm` directory, instead of `/usr/local/lib`
  - The `markdown-toc` script is installed to `$HOME/.npm/bin`
- `csv2md`: for converting tsv/csv tables to markdown tables
  - install with `pip3 install csv2md`

# Viewing the Site Locally

Run:

```
bundle exec jekyll serve --baseurl ''
```

See the following StackOverflow post for a reminder about why you need to add `--baseurl ''` to the end of the command: https://stackoverflow.com/a/19173888
