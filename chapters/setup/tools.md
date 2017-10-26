## Allow npm to Install Tools
> **[info] Fix npm permissions**
>
> [https://docs.npmjs.com/getting-started/fixing-npm-permissions#option-1-change-the-permission-to-npms-default-directory](https://docs.npmjs.com/getting-started/fixing-npm-permissions#option-1-change-the-permission-to-npms-default-directory)
>
> You need to give npm permission to install tools on your computer. Follow the link above to resolve the issue. "Option 1" works for most people.


## Install a Server to Host Web Pages

Install `create-next-app` by running the following command in the Terminal:

```bash
npm i -g create-next-app
```

> [info] This is the "shorthad" for `npm install --global create-next-app`. It's much quicker to type `i -g` than `install --global`, so why not?

"create-next-app" should now be installed.

## Setup a Project

In the Terminal, type the following commands:

`create-next-app my-amazing-app`
> [success] Creates a directory called "my-amazing-app" with projects files

> [danger] We need to `Shell Command Install code in PATH` like you did earlier...

`code my-amazing-app`
> [success] Launches VS Code with "my-amazing-app" as the working directory

## Browse Your Project Files

> [danger] Probably need screenshots to help build confidence


## Start Your Project

> [danger] Maybe a gif? 
command+R, shift+R, select `dev`

> [danger] Command click on link? Or just open a browser? Hmm...
Open `http://localhost:3000`


## Open Your `index.js` File

You'll notice a few folders and files in your project. For now, let's focus on `index.js` and we'll come back to the rest later.








> *[info] Explanation of Project Files*
>
> `.next`...
> `components`
> `node_modules`
> `pages`
> `static`
> `.gitignore`
> `next.config.js`
> `package.json`
> `README.md`
> `yarn.lock`