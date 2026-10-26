# Coding style

## Formatting

- Follow the [tidyverse style guide](https://style.tidyverse.org/). The [styler RStudio add-in](https://github.com/r-lib/styler) can format code.
- Use two-space indentation.
- Use ASCII characters and write names and comments in English.
- See [Sarah Johnson’s suggestions](https://gist.github.com/sj-io/3828d64d0969f2a0f05297e59e6c15ad) for additional guidance.

## Naming

Use `camelCase` for variables and `underscore_separated` names for functions. Prefix counts with `n`, such as `nSamples` and `nReads`. Use plural names for vectors and matrices, such as `reads`.

## R conventions

- Use braces for every `if` statement, including short ones.
- Use `library()` rather than `require()` so a missing package raises an error.
- Row names may be used as IDs in matrices and data frames.
- Use column and row names rather than fixed indices when their order could change.
- Use `for (i in seq_along(x))` rather than `for (i in 1:length(x))`; the latter fails for an empty vector.
- Use `ezLog` for logging where possible. Use `cat`, `print`, `ezWrite` or `message` when their output must be parsed later.
- Named functions should not depend on variables in the parent environment. Anonymous functions are the exception recorded in the project’s conventions.
