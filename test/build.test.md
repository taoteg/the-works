# Usage

- Requires Python 3.
- Requires an active virtual environment.
- Requires MarkdownTools.

## Basic Command

```
mdmerge -o OUTPUT.FILE.NAME.EXT INPUT.FILE.NAME.EXT
```

*Example:*
```
mdmerge -o output.test.000.md index.000.md
```

Results in a file named ```output.test.000.md``` comprised of all the source files listed in the input file ```index.000.md``` aggregated in the order they are listed.
