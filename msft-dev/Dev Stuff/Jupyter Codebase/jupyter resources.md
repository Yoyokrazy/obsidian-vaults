
--- 
- use [[nvm-windows]]
	- Node 16.14.2
	- npm 8.15.1

```
nvm use 16.14.2
node -v
npm -v
```

### Typical workflow

- Here's an example of a typical workflow:
	1. Sync to main (get your fork's main to match vscode-jupyter's main)
	2. Create branch
	3. `npm ci`
	4. `npm run clean`
	5. Start VS code Insiders root
	6. CTRL+SHIFT+B and build `Compile Web Views` and `Compile`
	7. Make code changes
	8. Write and [run](https://github.com/microsoft/vscode-jupyter/blob/29c4be79f64df1858692321b43c3079bb77bdd69/.vscode/launch.json#L252) unit tests if appropriate
	9. Test with `Extension` launch task
	10. Repeat until works in normal extension
	11. Test with `Extension (web)` launch task
	12. Run [jupyter notebook server](https://github.com/microsoft/vscode-jupyter/wiki/Connecting-to-a-remote-Jupyter-server-from-vscode.dev) to use in web testing
	13. Repeat until works in web extension
	14. Write integration tests and [run](https://github.com/microsoft/vscode-jupyter/blob/29c4be79f64df1858692321b43c3079bb77bdd69/.vscode/launch.json#L216) locally.
	15. Submit PR
	16. Check PR output to make sure tests don't fail.
	17. Debug [CI test failures](https://github.com/microsoft/vscode-jupyter/wiki/Tests)
