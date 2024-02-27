# Slim syntax highlighting for VS Code

The **Ruby Slim** extension brings [Slim template language](https://github.com/slim-template/slim) support to VS Code.
It fixes most issues in previous Slim extensions, aims to support more modern features such as
[Tailwind CSS](https://tailwindcss.com) and is well tested.

## Features

- A more complete [Tailwind CSS](https://tailwindcss.com) support, including:

  - [breakpoint prefixes](https://tailwindcss.com/docs/responsive-design) in class shortcuts (`.sm:text-center`)

  - [modifiers](https://tailwindcss.com/docs/responsive-design) in class shortcuts, even multiple ones (`.hover:dark:text-white`)

  - [opacity modifiers](https://tailwindcss.com/docs/text-color#changing-the-opacity) (`text-blue-600/50`)

  <img src="img/tailwind.png" width="600">

- Multiline attribute values:

  <img src="img/multiline_attribute_values.png" width="700">

- Multiline attributes wrapping:

  <img src="img/attribute_wrapping.png" width="500">

- Multiline comments:

  <img src="img/multiline_comments.png" width="300">

- Multiline attribute ruby expressions (this requires a Ruby syntax extension such as [Ruby LSP](https://github.com/Shopify/vscode-ruby-lsp)):

  <img src="img/multiline_ruby_expressions.png" width="400">

- Embedded languages: Ruby, JavaScript, Markdown, ERB, CSS, CoffeeScript, Sass, Less:

  <img src="img/markdown.png" width="500">

- More precise [scopes](https://macromates.com/manual/en/language_grammars#naming_conventions) for highlighting

  <img src="img/scopes.png" width="600">

- Developer goodies:
  - Full tests coverage
  - Grammar in a human-friendly format (YAML instead of JSON)

## Known Issues

- [Arbitrary values](https://tailwindcss.com/docs/adding-custom-styles#using-arbitrary-values) in class shortcuts (`.top-[117px]`) are
  [not supported](https://github.com/slim-template/slim/issues/906) by Slim and this extension.
- [Embedded language blocks](https://github.com/slim-template/slim?tab=readme-ov-file#embedded-engines-markdown-) with inline attributes are not supported:

      scss class="myClass":
        ...

## Release Notes

See the [Changelog](https://github.com/borama/vscode-ruby-slim/blob/main/CHANGELOG.md).

## Contributing

Please file an [Issue](https://github.com/borama/vscode-ruby-slim/issues) or [Pull Request](https://github.com/borama/vscode-ruby-slim/pulls) on the [GitHub repository](https://github.com/borama/vscode-ruby-slim).

See the wiki for some [development hints](https://github.com/borama/vscode-ruby-slim/wiki/Development-hints).

## Helpful links / Acknowledgements

- [My blog post about creating this extension]TBD
- [Syntax Highlighting Guide](https://code.visualstudio.com/api/language-extensions/syntax-highlight-guide) - official guide from the VS Code team
- [SublimeText Slim 2.0 grammar](https://github.com/SublimeText/Slim/blob/master/Syntaxes/Slim.sublime-syntax) - the basis of unit tests and a lot of inspiration comes from this well-maintained SublimeText grammar
- [Writing a TextMate Grammar: Some Lessons Learned](https://www.apeth.com/nonblog/stories/textmatebundle.html) - an older resource but still one of the best
- [Rubular](https://rubular.com/) is your best friend here
- as is a [good regexp manual](https://www.regextutorial.org)
- the [Slim extension](https://marketplace.visualstudio.com/items?itemName=sianglim.slim)
by Siang Lim that this one originates from
- the [vscode-ruby-lsp](https://github.com/Shopify/vscode-ruby-lsp) project has some nice Ruby/ERB [grammars](https://github.com/Shopify/vscode-ruby-lsp/tree/main/grammars)
