
--- 
### To-Do List
```tasks
not done
sort by status.type reverse
tag includes kernel
```
### Done
```tasks
done
tag includes kernel

```

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

### [[2023-04-05-We]] -- Brainstorming day
- [onDidRestartKernel ==> vscode-jupyter/types.ts at main](https://github.com/microsoft/vscode-jupyter/blob/main/src/kernels/types.ts#L467)
	- maybe useable for triggering the run all/above?
	- type `Event<T>`
	- [Potential useage of onDidRestart ==> vscode-jupyter/remoteJupyterServerMruUpdate.ts at main · GitHub](https://github.com/microsoft/vscode-jupyter/blob/main/src/kernels/jupyter/connection/remoteJupyterServerMruUpdate.ts#L30)
- [vscode-jupyter/notebookCommandListener.ts at main · microsoft/vscode-jupyter · GitHub](https://github.com/microsoft/vscode-jupyter/blob/main/src/notebooks/notebookCommandListener.ts#L83)
	- `notebookCommandListener.ts` seems to be where all the commands are registered/made.
	- not sure how involved my process will be, if its two pre-existing commands, might get away with building it right in ***here*** 

### [[2023-04-10-Mo]] -- Restart refactor
- two commands are redundant and needlessly confusing for new users
	- `notebookCommandListener.ts L#70-81 && L#89-96` 
	- okay got those cleaned up
- currently implementing a new command
- things I need to check
	- [ ] do I need a conditional context passing? kinda like the if statement for what the context is for Restart individually?
		- Probably just match the OG command, bc I'm going to call restart, so should likely match the process there.
	- need to update a number of files... #kernel 
		- [/] todo #kernel  `src/commands.ts`
			- need to sync with @Don on this
		- [x] todo #kernel  `src/platform/common/constants.ts` ✅ 2023-04-11
		- [/] todo #kernel `src/notebooks/notebookCommandListener.ts`
			- I think this is done?? but need to do some testing
		- [/] todo #kernel  `package.json` 
			- not sure on this one, need to check where I would even want it enabled/contributed. again, probably match `jupyter.restartkernel`
	- test it actually works lmao

### [[2023-04-11-Tu]] -- Restart + Run All Functionality
- weeeeeird stuff with the `commands.ts` file. Not totally sure how with vs without type mappings works, as it seems like there's no sort of cohesion there. 
	- there are mappings in the without interface, and vice versa in the with interface
- see todo's in above header for work to do.
- [ ] todo #kernel refactor the `commandtypemappings` within `src/commands.ts` to just collapse into one interface
- [ ] todo #kernel make sure to clean up the enablement within `package.json` for the command
- [ ] todo #kernel think about and explore contributions 

### [[2023-04-12-We]]
- well... `Restart + Run All` seems to work
- 