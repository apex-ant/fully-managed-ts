# Fully managed roblox-ts template for Roblox

This repository provides a fully managed roblox-ts template for Roblox development. It includes a pre-configured setup with essential tools and configurations for TypeScript.
Based on the work of https://github.com/SolarHorizon/fully-managed-rojo.git

## Project Structure
The project is organized as follows:

```
.
├── map/                    # Where workspace and other roblox studio files are generated, this folder is very important, do not delete or touch manually
├── src/                    # Standard roblox-ts source folder
├── build-project.(sh/bat)/ # Script to build initial roblox project
├── extract-assets.(sh/bat) # Script to extract assets from roblox project file, !!!!UNEXTRACTED CHANGES TO ROBLOX PROJECT WILL BE LOST IF NOT EXTRACTED!!!!!!!
└── install-env.(sh/bat)    # Script to install required tooling
```
## Requirements
 - Cargo
 - Node.js

## Workflow
1. **Install Environment**: Run `install-env.sh` (Linux/Mac) or `install-env.bat` (Windows) to set up the necessary tools.
2. **Build Project**: Use `build-project.sh` or `build-project.bat` to generate the initial Roblox project file.
3. **Run Rojo**: Start using `rojo serve` to sync your Luau source code with the Roblox project.
4. **Extract Assets**: If you make changes in Roblox Studio, run `extract-assets.sh` or `extract-assets.bat` to sync those changes back to your source files.
5. **PROFIT???**

## How to Commit Changes
1. Fetch changes
2. Build the project using `build-project.sh` or `build-project.bat`
3. Make changes in roblox studio or in the src folder
4. If you made changes in roblox studio run `extract-assets.sh` or `extract-assets.bat`
5. Commit all changes

## How to start project
In one terminal run `nodemon -w build.rbxl --exec ./extract-assets.sh` (Linux/Mac) or `nodemon -w build.rbxl --exec ./extract-assets.bat` (Windows) to automatically extract assets when the roblox project file changes.
In another terminal run `rojo serve` to start the Rojo server and sync code changes.
In yet another terminal run `npx rbxtsc -w` to compile typescript code to luau.

## Important Notes
- The `map/` directory is crucial for the Rojo setup. Do not delete or manually modify its contents.
- Always extract assets after making changes in Roblox Studio to avoid losing any unsaved work.
- To use install-env.sh` (Linux/Mac) or `install-env.bat` (Windows) cargo must be installed, to install cargo see https://rustup.rs/
