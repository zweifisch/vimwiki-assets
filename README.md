
style([markdown.css](http://kevinburke.bitbucket.org/markdowncss/)) and code
highlight(through [highlight.js](http://softwaremaniacs.org/soft/highlight/en/))
for html exported from vimwiki, also an export template for vimwiki

the vimwiki export setup in .vimrc

	let vimwiki_path='path/to/wiki/files/'
	let vimwiki_export_path='path/to/export/folder/'
	let wiki_settings={
	\ 'template_path': vimwiki_export_path.'assets/',
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

the `assets` folder should be put into the `vimwiki_export_path`
