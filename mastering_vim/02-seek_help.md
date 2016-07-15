# Seeking Help

If you are gonna use vim we should seek help. Vim has extensive documentation
but in order to browse it again you need vim.

## Direct Help

* `:help` will take use to help facility.

* `:help <topic><CR>` will take us to help page related to that topic

topic can be something like `regex` or `insert` if you wanna know something
related to insert in vim.

But most of the time we don't know what we are looking for so how do you get help
if you don't know what you are looking for. Vim can give you suggestions based on
couple of words

## Help with TAB

* `:help <topic><TAB>` will list matching topics that you can browse and complete

`:help map<TAB>` will list most of the topics related to `map` like recursive_mapping
or gui-mouse-mapping.

## Help with GREP

* `:helpgrep PATTERN` this will grep all help information that matching to pattern

PATTERN do not need slashes or other stuff for regular regexes.

`:helpgrep lookahead` will show all the help pages matching pattern lookahead.
Probably a lot so we need a way to browse them really easily.

## Browsing helpgrep result

* `:cnext` show me the next match in file
* `:cprev` show me the previous match in file
* `:cnfile` show me the next help file matching
* `:cpfile` show me the previous help file matching

> You dont have to do that but there is a configuration that maps arrow keys for
browsing helpgrep results. Here it is
  * -> : cnext
  * -> -> : cnfile
  * <- : cprev
  * <-<- : cpfile

Here is vimrc mapping for it.

    " Make it easy to navigate errors (and vimgreps)...
    nmap <silent> <RIGHT>         :cnext<CR>
    nmap <silent> <RIGHT><RIGHT>  :cnf<CR><C-G>
    nmap <silent> <LEFT>          :cprev<CR>
    nmap <silent> <LEFT><LEFT>    :cpf<CR><C-G>


Seems like helpgrep is special version of `VIMGREP`command which more general way
of searching something.

* `ZZ` quit from buffer with saving changes
* `wq` is another way to quitting buffer with saving changes.


## Full Pane Help Page

While looking for help inside vim, vim splits the screen so that you can also see
current buffer below help page. This is sometimes distracting so here is vimrc to
remove that pane and open help page in new tab.

    "=====[ Show help files in a new tab, plus add a shortcut for helpg ]==============

    "Only apply to .txt files...
    augroup HelpInTabs
        autocmd!
        autocmd BufEnter  *.txt   call HelpInNewTab()
    augroup END

    "Only apply to help files...
    function! HelpInNewTab ()
        if &buftype == 'help'
            "Convert the help window to a tab...
            execute "normal \<C-W>T"
        endif
    endfunction


## Extra

* `vimgrep /PATTERN/ files...`

Look for pattern in every file in the list and take me to each of them.
