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

* `:cnext` show me the next match
* `:cprev` show me the previous match
* `:cnfile` show me the next help file matching
* `:cpfile` show me the previous help file matching

> You dont have to do that but there is a function that maps arrow keys to
browsing helpgrep results. It maps follwing
  * -> : cnext
  * -> -> : cnfile
  * <- : cprev
  * <-<- : cpfile

Here is how to do it inside vimrc.

    " Make it easy to navigate errors (and vimgreps)...
    nmap <silent> <RIGHT>         :cnext<CR>
    nmap <silent> <RIGHT><RIGHT>  :cnf<CR><C-G>
    nmap <silent> <LEFT>          :cprev<CR>
    nmap <silent> <LEFT><LEFT>    :cpf<CR><C-G>
