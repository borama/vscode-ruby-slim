# Slim syntax highlighting for VSCode

The **Ruby Slim** extension brings [Slim template language](https://github.com/slim-template/slim) support to VSCode. It is inspired by the [Slim extension](https://marketplace.visualstudio.com/items?itemName=sianglim.slim) by Siang Lim
    but aims to support more modern features such as Tailwind CSS and is well tested.

## Features

- A more complete [Tailwind CSS](https://tailwindcss.com) support, including:
  - [breakpoint prefixes](https://tailwindcss.com/docs/responsive-design) in class shortcuts (`.sm:text-center`)
  - [modifiers](https://tailwindcss.com/docs/responsive-design) in class shortcuts, even multiple ones (`.hover:dark:text-white`)
  - [opacity modifiers](https://tailwindcss.com/docs/text-color#changing-the-opacity) (`text-blue-600/50`)

  <img src="img/tailwind.png">


- Multiline attributes wrapping:

  <img src="img/attribute_wrapping.png" style="max-width: 30em">

- Multiline comments:

  <img src="img/multiline_comments.png" style="max-width: 18em">

- Embedded languages: Ruby, JavaScript, Markdown, ERB, CSS, CoffeeScript, Sass, Less:

  <img src="img/markdown.png" style="max-width: 30em">


- More precise [scopes](https://macromates.com/manual/en/language_grammars#naming_conventions) for highlighting

- Developer goodies:

  - Full tests coverage
  - Grammar in a more human-readable format (YAML instead of JSON)

## Known Issues

- [Arbitrary values](https://tailwindcss.com/docs/adding-custom-styles#using-arbitrary-values) in class shortcuts (`.top-[117px]`) are
  [not supported](https://github.com/slim-template/slim/issues/906) by Slim nor by this extension.

- Multiline ruby expressions in HTML attribute values are not supported (this would probably require [semantic
  highlighting](https://code.visualstudio.com/api/language-extensions/semantic-highlight-guide) / LSP).

## Release Notes

0.9 Initial release

## Development

### Helpful links

- [My blog post about creating this extension]TBD
- [Syntax Highlighting Guide](https://code.visualstudio.com/api/language-extensions/syntax-highlight-guide) - official guide from the VSCode team
- [SublimeText Slim 2.0 grammar](https://github.com/SublimeText/Slim/blob/master/Syntaxes/Slim.sublime-syntax) - this extension gets a lot of inspiration from this SublimeText grammar
- [Writing a TextMate Grammar: Some Lessons Learned](https://www.apeth.com/nonblog/stories/textmatebundle.html) - an older resource but still one of the best
- [Rubular](https://rubular.com/) is your best friend here
- as is a [good regexp manual](https://www.regextutorial.org)

### YAML compilation

```bash
npx js-yaml syntaxes/slim.tmLanguage.yaml > syntaxes/slim.tmLanguage.json
npx js-yaml syntaxes/interpolated-ruby.yaml > syntaxes/interpolated-ruby.json
```

### Tests run

See the [vscode-tmgrammar-test](https://github.com/PanAeon/vscode-tmgrammar-test) project.

```sh
npx vscode-tmgrammar-test \
    -g syntaxes/slim.tmLanguage.json \
    -g tests/support_grammars/html.tmLanguage.json \
    -g tests/support_grammars/ruby.tmLanguage.json \
    -g tests/support_grammars/coffeescript.tmLanguage.json \
    -g tests/support_grammars/css.tmLanguage.json \
    -g tests/support_grammars/less.tmLanguage.json \
    -g tests/support_grammars/erb.tmLanguage.json \
    -g tests/support_grammars/JavaScript.tmLanguage.json \
    -g tests/support_grammars/markdown.tmLanguage.json \
    -g tests/support_grammars/scss.tmLanguage.json \
    -g tests/support_grammars/sass.tmLanguage.json \
    -g tests/support_grammars/html-derivative.tmLanguage.json \
    tests/syntax_test_slim.slim > results.txt
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
