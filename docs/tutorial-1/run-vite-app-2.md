---
sidebar_position: 2
---

# Run vite app

## 1) Go to Guides page:
[https://bun.sh/guides](https://bun.sh/guides)
![Guides link](./img/guides-link.png)


## 2) Find section:
Find section "Build a frontend using Vite and Bun" and click to link:

[https://bun.sh/guides/ecosystem/vite](https://bun.sh/guides/ecosystem/vite)
![Guides link](./img/guides-marked-link.png)

## 3) We will use this page to build application:

![Guides link](./img/build-vite-app-docs.png)

### 3.1) Run this command to start creating application process:

```shell
bun create vite my-app
```
Where `my-app` is your desired application name.
* Choose React:
![](./img/choose-react.png)
* Then choose Typescript + SWC:
![](./img/choose-typescript-swc.png)

### 3.2) Go to app folder, install dependencies and run application:
```bash
cd my-app
bun install

bunx --bun vite
```

* Open this link in browser:
![](./img/follow-the-app-link.png)

* You should see something like this:
![](./img/vite-react-index-page.png)

## Other

* You can change dev command in package.json to this command:
`bunx --bun vite`
![](./img/dev-package-json.png)
and run the application with this command:
`bun run dev`
