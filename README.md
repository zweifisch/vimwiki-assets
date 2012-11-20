
style([markdown.css](http://kevinburke.bitbucket.org/markdowncss/)) and code
highlight(through [highlight.js](http://softwaremaniacs.org/soft/highlight/)
for html exported from vimwiki, also an export template for vimwiki

first, some setup in .vimrc
```vim
let vimwiki_path='path/to/wiki/files/'
let vimwiki_export_path='path/to/export/folder/'
let wiki_settings={
\ 'template_path': vimwiki_export_path.'vimwiki-assets/',
\ 'template_default': 'default',
\ 'template_ext': '.html',
\ 'auto_export': 0,
\ 'nested_syntaxes': {
\ 'js':'javascript',
" more langs...
\ }}

let wikis=["your_wiki","another_wiki","more_topics..."]
let g:vimwiki_list = []
for wiki_name in wikis
	let wiki=copy(wiki_settings)
	let wiki.path = vimwiki_path.wiki_name.'/'
	let wiki.path_html = vimwiki_export_path.wiki_name.'/'
	let wiki.diary_index = 'index'
	let wiki.diary_rel_path = 'diary/'
	call add(g:vimwiki_list, wiki)
endfor
```

then, get this repo
```sh
mkdir -p path/to/export/folder
cd !$
git clone https://github.com/zweifisch/vimwiki-assets
```

finally, open an wiki run `:VimwikiAll2HTML`
