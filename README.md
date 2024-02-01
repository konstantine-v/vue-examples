# vue-examples

This project is meant to show off my ability using and deploying Vue/Vite applications. 

## Goals
The main goal is to achieve a base application relying almost entirely off documentation alone as that's something I strive for when working with something new.

I've used Vue in the past but this is specifically to learn the latest version, Vite, and the different APIs offered.

Authentication and permissions will be an afterthough since I'm more worried about the Front-End portion of this rather than any potential back-end features, although the goal will be to add it in without relying on very much back-end code.

## Regarding the setup
This project [utilizes bun](https://bun.sh/docs/installation) since it's easier to setup and manage for projects

I've opted for using [TailwindCSS](https://tailwindcss.com/) to make building components easier. Other options are a bit too cumbersome.

Finally, I've included ESLint for linting later on.


## Project Setup
```sh
bun install
```

### Compile and Hot-Reload for Development
```sh
bun run tailwindcss -i ./src/assets/base.css -o ./src/assets/m
ain.css #Build CSS Library
bun run dev #Run site
```

### Compile and Minify for Production
```sh
bun run build
```

### Lint with [ESLint](https://eslint.org/)
```sh
bun run lint
```
