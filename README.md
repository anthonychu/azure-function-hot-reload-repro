# Hot Reload Repro

This is a Repository that contains the reproduction for a bug regarding Hot Reload in the Azure Functions.

# Running locally
- Install Azure Function Core Tools
- `npm i` / `yarn`
- `npm run start` / `yarn start`

# Reproducing the bug
- Get the function running locally
- `curl http://localhost:7071/api/Test`
- Observe the logged output  
- Make a change, for example: `Hello World` to `Hello Universe`
- Rerun `curl http://localhost:7071/api/Test`
- The logging output doesn't change! The compiled js file did.

# Possible Cause of the Bug
This only happens when you start the function with `--script-root` or `--prefix` or `cd src && func start`.
The function doesn't seem to restart after the recompilation.

# Environment
```
func --version
3.0.3568

OS
Manjaro Linux 21.0.7 Ornara
```