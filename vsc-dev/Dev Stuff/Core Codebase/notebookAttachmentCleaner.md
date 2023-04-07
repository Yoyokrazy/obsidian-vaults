`PATH = \vscode\extensions\ipynb\src\notebookAttachmentCleaner.ts`
[vscode/notebookAttachmentCleaner.ts · microsoft/vscode · GitHub](https://github.com/microsoft/vscode/blob/4eb8467961aae3f118c0a652abe68d5a0898579d/extensions/ipynb/src/notebookAttachmentCleaner.ts)

### Thoughts
- needs a rework and adoption of [[notebookWillSave API]]
- probably needs cleanup for readability's sake

### 3/29
- two cases for attachment cleaning: autosave and not
	- autosave
		- user will never trigger the [[notebookWillSave API]], therefore  being entirely handled by the `didChangeTextDoc` debouncer
	- NO autosave
		- for the most part this is the same, but changes if the user explicitly hits cmd-s right after deleting some markdown. 
		- There is a chance that the notebook will save, become clean, THEN the debounce will trigger, altering the metadata, and creating a dirty notebook
		- Likely will confuse the user, as they will see their notebooks formatted, and know they hit save, then see an immediately dirty notebook