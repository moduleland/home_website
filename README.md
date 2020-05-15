## Welcome to land 

If you are looking for a package manager with CLI and complete integration with all your github repositories, their respective releases and a complete deployment of new ones without doing anything boilerplating like `npm publish`, this is your land. 

This is like npm, but __deno__ right.

### Help us

- [discord](https://discord.com/invite/2eqenPy)

### How it works

- Open your terminal and type `deno install -Af https://module.land/cli/land.js` 
- Check if the command works with `land -v`
- On a _new_ project folder type `land add moduleland/pdeno-lib@1.0.0`

You see that? A new json emerged, you are creating land!

- Open `land.json` file, we are gonna inspect what's inside
```json
{
  "imports": {
    "moduleland/deno-lib@1.0.0/": "https://v1.module.land/public/moduleland/deno-lib@1.0.0/"
  }
}
```
The `imports` object, defines the aliases you can use to import inside your project, without using all the long url.

- Create a _new_ file `main.ts` and type the following code
```ts
import { foo, fighters } from 'moduleland/deno-lib@1.0.0/main.ts';

console.log(foo(), fighters(2))
```

- Now, run the this code with `land run main.ts`, add all the flags you need, deno has a lot of cool ones!

```sh
Hello land! 4
```
Really nice, now we have a deno project running with __land__.

--------

Now, you are ready for start sharing your first module, __log in__ and share your project from __github__, use the knowledge from the example to integrate your module. 

Remember, if you make a __new release__ about yout code, you don't need to tell `land` what to do, the __new version__ is gonna be available at the same time.

### More

We are gonna update `deno-lib@1.0.0` reference, it's a very old module
- Open your terminal inside the project and type `land update moduleland/deno-lib@2.0.0`
- Now, type `land run main.ts` and the following is gonna blow your mind
```sh
Hello land 2.0.0! 6
```
You didn't change your code, and the results are different. Let's check out the `land.json` and `main.ts` files.
```json
{
  "imports": {
    "moduleland/deno-lib@2.0.0/": "https://v1.module.land/public/moduleland/deno-lib@2.0.0/"
  }
}
```
```ts
import { foo, fighters } from 'moduleland/deno-lib@2.0.0/main.ts';

console.log(foo(), fighters(2))
```
`land update` check all the references inside your project and makes an update for you, so you don't need to worry if you lose the trace from a file.

- We will update the project once more, but without specifying the version `land update moduleland/deno-lib`
- Type `land run main.ts`
```sh
Hello *latest* land! 8
```
Now, the module is on the latest version of the default branch of the project.

Check this example on [github](https://github.com/moduleland/deno-lib) and [moduleland/deno-lib](https://module.land/~moduleland/deno-lib)
