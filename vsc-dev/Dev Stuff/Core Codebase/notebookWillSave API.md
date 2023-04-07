`PATH = /vscode/src/vscode-dts/vscode.proposed.notebookDocumentWillSave.d.ts`
[vscode.dev -- proposed.notebookDocumentWillSave.d.ts](https://insiders.vscode.dev/github/microsoft/vscode/tree/d3c2dcacf39c2a25c06547945ae13da4c8cf9f82)

### Thoughts
- adopt this within [[notebookAttachmentCleaner]]
- requires a `workspaceEdit` to be returned to it
- code example: [notebook-will-save/extension.ts  rebornix/notebook-will-save ](https://github.com/rebornix/notebook-will-save/blob/main/src/extension.ts#L17-L25)
- 