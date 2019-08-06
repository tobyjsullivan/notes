# bash

## Best Practices

### Exit on error

```bash
set -o errexit # shortcut: -e
```

Immediately aborts the script on first error.

### Catch failures in pipelines

```bash
set -o pipefail
```

Causes pipelines to return an exit status if the last command fails.

### Restrict usage of undefined variables

```bash
set -o nounset # shortcut: -u
```

Throws an error if there is an attemt to read from an undefined variable.

### Use a main method

```bash
main() {
  # ...
}

main "@$"
```

Readability and maintainability of longer scripts is improved by breaking logic into well-named functions.
Using a `main` function avoids distributing top-level code around these other functions.

Pro tip: don't bother for scripts <20 lines.

