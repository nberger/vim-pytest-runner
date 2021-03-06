# pytest-runner.vim

This is a fork of [vim-rspec](https://github.com/thoughtbot/vim-rspec) to run py.test in a similar fashion.

## Installation

Recommended installation with [vundle](https://github.com/gmarik/vundle):

```vim
Bundle 'mindriot101/vim-pytest-runner'
```

If using zsh on OS X it may be necessary to move `/etc/zshenv` to `/etc/zshrc`.

## Configuration

### Key mappings

Add your preferred key mappings to your `.vimrc` file. For example:

```vim
" pytest-runner.vim mappings
map <Leader>t :call RunCurrentTestFile()<CR>
map <Leader>s :call RunNearestTest()<CR>
map <Leader>l :call RunLastTest()<CR>
map <Leader>a :call RunAllTests()<CR>
```

### Custom command

Overwrite the `g:pytest_command` variable to execute a custom command.

Example:

```vim
let g:pytest_command = "!py.test -s {test}"
```

This `g:pytest_command` variable can be used to support any number of test
runners or pre-loaders. For example, to use
[Dispatch](https://github.com/tpope/vim-dispatch):

```vim
let g:pytest_command = "Dispatch py.test {test}"
```

### Custom test finder

If you've customised your test finder from the standard "^test", the same searcher can be used when finding a single test with `RunNearestTest` as follows:

``` vim
let g:test_regexp = "\v\s*(.*def)\s+test_"
```

to ensure an underscore at the beginning of the test function.

Credits
-------

The conversion to py.test was performed and maintained by Simon Walker.

The original rspec.vim is maintained by [thoughtbot, inc](http://thoughtbot.com/community)
and [contributors](https://github.com/thoughtbot/vim-rspec/graphs/contributors)
like you. Thank you!

It was strongly influenced by Gary Bernhardt's [Destroy All
Software](https://www.destroyallsoftware.com/screencasts) screencasts.

