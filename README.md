# tree-sitter-ghostty

> [!WARNING]
> This is still **experimental**

Tree-sitter grammar/parser for [Ghostty] configuration files

## How to use

### Neovim

> [!IMPORTANT]
> Requires [nvim-treesitter]

1. Add this in your Lua config

```lua

local parsers = require('nvim-treesitter.parsers')

-- Register this parser manually to nvim-treesitter's parser directory
parsers.ghostty = {
    install_info = {
        url = 'https://github.com/bezhermoso/tree-sitter-ghostty',
        files = { 'src/parser.c' },
        requires_generate_from_grammar = true,
    },
}

-- Associate this parser to the `ghostty` file-type
vim.treesitter.language.register('ghostty', { 'ghostty' })
```

2. Re-open Neovim & run `:TSInstall ghostty`. Follow prompts.

3. Copy `./queries/highlights.scm` to `~/.config/nvim/queries/ghostty/highlights.scm`

4. Open your Ghostty config and set its file-type to `ghostty`:

```
:set ft=ghostty
```

You can also add this line to the top of your Ghostty config:

```diff
+# vim: ft=ghostty
 #
 # The rest of your Ghostty configuration 👻...
```

# TODOs

- [ ] Tests
- [ ] Contribute queries to [nvim-treesitter]

[Ghostty]: https://ghostty.org
[nvim-treesitter]: https://github.com/nvim-treesitter/nvim-treesitter