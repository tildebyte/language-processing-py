##### Configuring (hacking) linters
Add `'source.python.pyde'` to the `grammarScopes` list in the `provideLinter` function, e.g.:

```js
export function provideLinter() {
  return {
    name: 'Pylint',
    grammarScopes: ['source.python', 'source.python.django', 'source.python.pyde'],

```

As stated, pretty hacky and non-maintainable, but hey, it works.

##### Ignoring Processing's reserved symbols.

I can't get [`linter-flake8`](https://github.com/AtomLinter/linter-flake8) to ignore the (large number of) Processing symbols.

[`Pylint`](https://github.com/AtomLinter/linter-pylint) is relatively easy to configure. Use the `.pylintrc` from this repo, or at least add the list of Processing symbols from it to `additional-builtins` in the `[Variables]` section in yours.
