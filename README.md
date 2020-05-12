## Welcome to module.land!

*land everywhere*

### What is this?
A __deno__ module manager for your private and public modules hosted on __github__.

### Why?
On production environments, private repositories and ways to safely delivery code, are a need.
This project solves this problems and provides a complete environment of work.
We know one of the principles of __deno__ is about the no centralziation, but your code is on __github__... no?

### But...
If you have any question, you can enter our [discord](https://discord.gg/2eqenPy)!

### How to use it?
#### Account
- **Log in** with your github account
- **Find** and **add** your module
#### CLI
- **Install the cli** using `deno install -A -f https://module.land/cli/land.js` in the terminal
- **Add** a module on your project with `land add <username>/<repo>` or specify the version with `@<version>`
- **Run** your module with `land run <args>` args are the same as deno
#### Your code
- Import your module directly on your code.
```ts
import { foo } from 'username/example@1.0.2/utils/functions.ts';
import somethingBig from 'username/example@1.0.2/utils/somethingBig.ts';

console.log(foo())
```
#### More...
- **Update** your modules with `land update <username>/<repo>` or specify the version with `@<version>`
