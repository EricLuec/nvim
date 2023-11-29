![1 UcYgBH0kIS4bpjflwRjJ4g](https://github.com/EricLuec/nvim/assets/140081980/46e80dfe-b63a-4da8-9d27-3493551c5837)

# Introduction

Now that we all know that I became a superior human beeing, lets break my config down ant list the shortcuts increase workflow to a blazing 400%.

# TableofContents

1. [Introduction](#Introduction)
2. [Table of Contens](#TableofContents)
3. [Plugins / Layout](#Plugins/Layout)
4. [LSP](#LSP)
5. [Telescope](#Telescope)
6. [TreeSitter](#TreeSitter)
7. [UndoTree](#UndoTree)
8. [Harpoon](#Harpoon)
9. [Contact](#Contact)


# Plugins/Layout

Packer is used to install LSP, Telescope, Treesitter, UndoTree, Harpoon (Yes Primeagen-Fanboy, sho0t me)

# LSP

Folgende Remaps wurden verwendet:

```bash
local cmp_mappings = lsp.defaults.cmp_mappings({
  ['<C-p>'] = cmp.mapping.select_prev_item(cmp_select),
  ['<C-n>'] = cmp.mapping.select_next_item(cmp_select),
  ['<C-y>'] = cmp.mapping.confirm({ select = true }),
  ["<C-Space>"] = cmp.mapping.complete(),
})

cmp_mappings['<Tab>'] = nil
cmp_mappings['<S-Tab>'] = nil

lsp.setup_nvim_cmp({
  mapping = cmp_mappings
})

lsp.set_preferences({
    suggest_lsp_servers = false,
    sign_icons = {
        error = 'E',
        warn = 'W',
        hint = 'H',
        info = 'I'
    }
})

lsp.on_attach(function(client, bufnr)
  local opts = {buffer = bufnr, remap = false}

  vim.keymap.set("n", "gd", function() vim.lsp.buf.definition() end, opts)
  vim.keymap.set("n", "K", function() vim.lsp.buf.hover() end, opts)
  vim.keymap.set("n", "<leader>vws", function() vim.lsp.buf.workspace_symbol() end, opts)
  vim.keymap.set("n", "<leader>vd", function() vim.diagnostic.open_float() end, opts)
  vim.keymap.set("n", "[d", function() vim.diagnostic.goto_next() end, opts)
  vim.keymap.set("n", "]d", function() vim.diagnostic.goto_prev() end, opts)
  vim.keymap.set("n", "<leader>vca", function() vim.lsp.buf.code_action() end, opts)
  vim.keymap.set("n", "<leader>vrr", function() vim.lsp.buf.references() end, opts)
  vim.keymap.set("n", "<leader>vrn", function() vim.lsp.buf.rename() end, opts)
  vim.keymap.set("i", "<C-h>", function() vim.lsp.buf.signature_help() end, opts)


```

# Telescope

# TreeSitter

# UndoTree

# Harpoon

# Contact

As always, GitHub DMs or open an issue.




