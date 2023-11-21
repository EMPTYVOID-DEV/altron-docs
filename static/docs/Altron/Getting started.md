# Getting started

You have to use **Altron** inside a svelte project , if you haven't start one yet try one these setups:

### Sveltekit setup

```Bash
npx create-svelte@latest
```

### Astro setup

```Bash
npx create-astro@latest
```

### create-split-app

[create-split-app](https://create-split-app.vercel.app) is a cli tool built to setup a project with most modern technologies **Sveltekit**, **Tailwind**, **Prisma**, **Lucia** , **Typescript** , **Zod** .

```Bash
npx create-split-app@latest
```

### Installing Altron


#### npm

```Bash
npm install @altron/altron@latest
```

#### yarn

```Bash
yarn add @altron/altron@latest
```

#### pnpm

```Bash
pnpm i @altron/altron@latest
```

### Basic usage

``` Typescript
<script>
  import  {Altron}  from '@altron/altron';
</script>

<Altron />
```
