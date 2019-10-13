# yamenu
Yet Another Menu plugin for vim.


## Why

As I have some mappings/commands which are used occasionally (but not often enough to make them stay in my
muscle memory), I wanted a simple and fast way to see all those not so frequently used commands.


# Usage

![Example usage](https://rikulaa.github.io/images/vim-yamenu.gif)

Menus are created with dictionaries. The corresponding key for each entry is used for the selecting the option.
The options have two main keys: `title` (Simple description) and `execute` (vimscript to be executed).
You can also create nested menus by providing additional dictionary in the `menu` key.

When calling the `yamenu#Show()` new menu window will be opened up the bottom half of the screen.

To create a simple menu:
```vim
let g:menu = {
            \'h': {'title': "Say hello", 'execute': 'echo "Hello world!"' },
            \'s': {'title': "Open another submenu", 'menu': { 'f': { 'title': "Print filename", 'execute': "echo expand('%')"}, 'u': {'title': 'Another very useful command'} }}
            \}

" And map it to <leader>m
nnoremap <silent> <leader>m  :call yamenu#Show(g:menu)<CR>

```

## Alternatives

[quickmenu](https://github.com/skywind3000/quickmenu.vim)  
[vim-venu](https://github.com/Timoses/vim-venu)
