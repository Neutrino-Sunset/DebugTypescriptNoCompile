# Debug Typescript no compile

This project demonstrates how Typescript files can be debugged in Nodejs without transpiling to Javascript first.

Create a directory and initialise as a node project. Make the entrypoint a typescript file e.g. Main.ts accept other defaults.

    > npm init


Install required libraries.

    > npm i -D typescript ts-node @types/node

   * typescript - core typescript language support.
   * ts-node - node typescript support.
   * @types/node - type definitions for node builtin types. (Needed for VSCode Intellisense).

Create tsconfig.json. No changes are required to the default file.

    > tsc --init

Generate VSCode launch config. A simple config would be something like this:

    "name": "Debug",
    "type": "node",
    "request": "launch",
    "args": ["${workspaceRoot}/Main.ts"],
    "runtimeArgs": ["-r", "ts-node/register"],
    "protocol": "inspector",
    "internalConsoleOptions": "openOnSessionStart"
    

