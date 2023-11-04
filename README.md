# ruby-slim

**This is alpha software, not ready for use…**

The Ruby Slim extension brings [Slim template language](https://github.com/slim-template/slim) support to VSCode. It is inspired by the [Slim extension](https://marketplace.visualstudio.com/items?itemName=sianglim.slim) but supports all modern features such as Tailwind CSS.

## Features

- Full Tailwind support (responsive prefixes `:`, arbitrary values in `[]`, etc.)

## Extension Settings


## Known Issues


## Release Notes


0.0.1 Initial release


## Development

### YAML compilation

```bash
npx js-yaml syntaxes/slim.tmLanguage.yaml > syntaxes/slim.tmLanguage.json
npx js-yaml syntaxes/interpolated-ruby.yaml > syntaxes/interpolated-ruby.json
```

### Tests run

```bash
npx vscode-tmgrammar-test -g syntaxes/slim.tmLanguage.json -g tests/support_grammars/html.tmLanguage.json -g tests/support_grammars/ruby.tmLanguage.json -g tests/support_grammars/coffeescript.tmLanguage.json -g tests/support_grammars/css.tmLanguage.json -g tests/support_grammars/less.tmLanguage.json -g tests/support_grammars/erb.tmLanguage.json -g tests/support_grammars/JavaScript.tmLanguage.json -g tests/support_grammars/markdown.tmLanguage.json -g tests/support_grammars/scss.tmLanguage.json tests/syntax_test_slim.slim -g tests/support_grammars/sass.tmLanguage.json -g tests/support_grammars/html-derivative.tmLanguage.json > results.txt
```

### Slim output test

```bash
echo "markdown:
  <br aa=\"#{bb}\">" | slimrb -s -l '{ bb: "something" }'

```

### Pack extension

```bash
npx vsce package
```
