
--- 
### Kernel Restart
- well what the hell are kernels
- how do I `restart` them
- ***Kai thought*** = does a `restart` return a `promise` saying they're completed successfully? 
	- need to be coupled together with the run all/above commands

### Run All/Above
- runs all cells *OR* all above the focused cell
- functionality:
	- coupled do the end of a restart
	- UX

### [[2023-04-05-We]]
- [onDidRestartKernel ==> vscode-jupyter/types.ts at main](https://github.com/microsoft/vscode-jupyter/blob/main/src/kernels/types.ts#L467)
	- maybe useable for triggering the run all/above?
	- type `Event<T>`
	- [Potential useage of onDidRestart ==> vscode-jupyter/remoteJupyterServerMruUpdate.ts at main · GitHub](https://github.com/microsoft/vscode-jupyter/blob/main/src/kernels/jupyter/connection/remoteJupyterServerMruUpdate.ts#L30)
- [vscode-jupyter/notebookCommandListener.ts at main · microsoft/vscode-jupyter · GitHub](https://github.com/microsoft/vscode-jupyter/blob/main/src/notebooks/notebookCommandListener.ts#L83)
	- `notebookCommandListener.ts` seems to be where all the commands are registered/made.
	- not sure how involved my process will be, if its two pre-existing commands, might get away with building it right in ***here*** 

[[2023-04-10-Mo]]
- two commands are redundant and needlessly confusing for new users
	- `notebookCommandListener.ts L#70-81 && L#89-96` 
	- okay got those cleaned up
- currently implementing a new command
- things I need to check
	- [ ] do I need a conditional context passing? kinda like the if statement for what the context is for Restart individually?
		- Probably just match the OG command, bc I'm going to call restart, so should likely match the process there.
	- need to update a number of files...
		- [ ] `src/commands.ts`
		- [ ] `src/platform/common/constants.ts`
		- [ ] `src/notebooks/notebookCommandListener.ts`
		- [ ] `package.json` 
			- not sure on this one, need to check where I would even want it enabled/contributed. again, probably match `jupyter.restartkernel`
	- test it actually works lmao