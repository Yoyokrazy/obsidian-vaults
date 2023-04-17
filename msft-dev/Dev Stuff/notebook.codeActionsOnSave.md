[Explore support for \`notebook.codeActionsOnSave\` · Issue #179213 · microsoft/vscode · GitHub](https://github.com/microsoft/vscode/issues/179213)

--- 
- list of user adjustable actions that happen just before save
- integrate with `formatOnSave`
- features:
	- notebook specific features
		- move all imports to top
		- delete empty cells
	- language server has things?
	- linting?


any command that can take care of notebook documents
- we already have codeactions for cells (bc they are text documents)

save participants
	- format on save -- runs in core
	- onwillsavenotebook doc  -- runs against ext host
	- codeactionsonsave