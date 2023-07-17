# Nextjs v13.2 with TypeScript, Prettier and ESLint

## Table of Contents

- [Nextjs v13.2 with TypeScript, Prettier and ESLint](#nextjs-v132-with-typescript-prettier-and-eslint)
  - [Table of Contents](#table-of-contents)
  - [Tech Stack](#tech-stack)
  - [Other Technologies](#other-technologies)
  - [Project Description](#project-description)
  - [Step-by-step (from scratch) Instructions](#step-by-step-from-scratch-instructions)
  - [Quickstart Instructions](#quickstart-instructions)

## Tech Stack

<div align="left" width="100%">
  <img src="https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB" alt="React Badge"/>
  <img src="https://img.shields.io/badge/TypeScript-3178C6.svg?style=for-the-badge&logo=TypeScript&logoColor=white" alt="TypeScript Badge"/>
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E.svg?style=for-the-badge&logo=JavaScript&logoColor=black" alt="JavaScript Badge"/>
  <img src="https://img.shields.io/badge/HTML5-E34F26.svg?style=for-the-badge&logo=HTML5&logoColor=white" alt="HTML Badge"/>
  <img src="https://img.shields.io/badge/CSS3-1572B6.svg?style=for-the-badge&logo=CSS3&logoColor=white" alt="CSS Badge"/>
  <img src="https://img.shields.io/badge/Tailwind%20CSS-06B6D4.svg?style=for-the-badge&logo=Tailwind-CSS&logoColor=white" alt="CSS Tailwind Badge"/>
  <img src="https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white" alt="Node.js Badge"/>
  <img src="https://img.shields.io/badge/Next.js-000000.svg?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="Next.js Badge"/>
  <img src="https://img.shields.io/badge/Vercel-000000.svg?style=for-the-badge&logo=Vercel&logoColor=white" alt="Vercel Badge"/>
</div>

## Other Technologies

<div>
  <img src="https://img.shields.io/badge/React_Icons-61DAFB.svg?style=for-the-badge&logo=React&logoColor=black" alt="React Icons"/>
  <img src="https://img.shields.io/badge/Google%20Fonts-4285F4.svg?style=for-the-badge&logo=Google-Fonts&logoColor=white" alt="Google Fonts"/>
</div>

## Project Description

Setup with me Next.js v13.2 with TypeScript, Prettier, and ESLint.

## Step-by-step (from scratch) Instructions

1. Open your Windows powershell or MacOS terminal and write the following command (write your own project name where project-orbis is):

   ```bash
   $ npx create-next-app@13.2 --typescript project-orbis
   ```

2. On installation you should see the following prompts:\
   Would you like to use ESLint with this project? No / <a href="https://github.com/quyencodes/nextjs13.2-setup">Yes</a>\
   Would you like to use `src/` directory with this project? <a href="https://github.com/quyencodes/nextjs13.2-setup">No</a> / Yes\
   Would you like to use experimental `app/` directory with this project? <a href="https://github.com/quyencodes/nextjs13.2-setup">No</a> / Yes\
   What import alias would you like configured? <a href="https://github.com/quyencodes/nextjs13.2-setup">@</a> / \*

   ```bash
   $ cd project-orbis/
   $ code .
   ```

3. Open the terminal with `ctrl + backtick mark` and write the following command:

   ```bash
   npm run dev
   ```

4. Remove the following lines of code and files:

   1. Navigate into `pages/index.tsx` and do the following:

   - Remove the existing `<main>...</main>` element and replace it with `<main>New Project</main>`.

   - Remove at the top of index.tsx:

   ```js
   import Image from 'next/image'
   import { Inter } from 'next/font/google'
   import styles from '@/styles/Home.module.css'

   const inter = Inter({ subsets: ['latin'] })
   ```

   1. Navigate into `styles/Home.module.css` and remove the entire file
   2. In `globals.css` remove all the existing lines of code
   3. <b>(CHECKPOINT)</b> When you navigate to `localhost:3000` it should be a completely white page with text "New Project"

5. Now we will be using <a href="https://tailwindcss.com/docs/guides/nextjs">Tailwind CSS - Next.js framework guide </a> to install Tailwind CSS to our project

   ```bash
   $ npm install -D tailwindcss postcss autoprefixer
   $ npx tailwindcss init -p
   ```

   In our `tailwind.config.js` add the following code into content:

   ```js
   module.exports = {
     content: [
       './app/**/*.{js,ts,jsx,tsx,mdx}',
       './pages/**/*.{js,ts,jsx,tsx,mdx}',
       './components/**/*.{js,ts,jsx,tsx,mdx}',
     ],
     theme: {
       extend: {},
     },
     plugins: [],
   }
   ```

   Now add the `@tailwind` directives for each Tailwind's layers to the `globals.css` file

   ```css
   @tailwind base;
   @tailwind components;
   @tailwind utilities;
   ```

   Rebuild the client by running the command in the terminal:

   ```bash
   $ ctrl + c
   npm run dev
   ```

6. Now navigate to <a href="https://fonts.google.com/" target="_blank">`Google Fonts`</a> and select the fonts you'd like to use for your project. For this demonstration I use Inter and Montserrat. Select all the choices (100, 200, 300...) and all the styles (light, regular, bold...) for the font.

   Now select the `<link>` embed option and copy the code into the `<head>` of our html. This will be in our `pages/_document.tsx` file. Expand the `<Head/>` element to be `<Head>{link embed here}</Head>` and put the link embed right in between the `<Head>` element. Make sure to close the link elements.

7. Return back to `tailwind.config.js` and add the fonts you selected as a <a href="https://v2.tailwindcss.com/docs/font-family#customizing" target="_blank">custom font</a> by editing the `theme.fontFamily` section:
   ```js
   theme: {
     extend: {
      fontFamily: {
        bodyFont: ["Montserrat", "sans-serif"],
        titleFont: ["Inter", "sans-serif"]
      }
     },
   },
   ```
8. Lastly, add colors, responsiveness, and other custom properties to your <a href="https://tailwindcss.com/docs/configuration" target="_blank">tailwind.config.js</a>, refer to my completed tailwind.config.js <a href="" target="_blank">here</a>.

9. Add a `components` folder to your root directory and start developing

10. For prettier AND prettier with tailwindcss, add a `.prettierrc` file, feel free to copy the one <a href="https://github.com/quyencodes/nextjs13.2-setup/blob/main/.prettierrc" target="_blank">here</a> and run the command:

```bash
$ npm install -D prettier prettier-plugin-tailwindcss
```

11. Now you can add existing code that lives on your local device up to GitHub via this <a href="https://docs.github.com/en/migrations/importing-source-code/using-the-command-line-to-import-source-code/adding-locally-hosted-code-to-github" target="_blank">article</a>

## Quickstart Instructions

1. Fork and clone the repository:
   ```bash
   $ git clone https://github.com/quyencodes/nextjs-13.2.git
   ```
2. Open the terminal with `ctrl + backtick mark`, make sure to <b>change to the correct directory</b> and write the following command (install NPM packages):
   ```bash
   npm install
   ```
3. Open a seperate terminal window and write the following command:
   ```bash
   npm run dev
   ```
4. Project will be deployed on a localhost server, navigate to your browser and enter in the url:
   ```bash
   http://localhost:3000
   ```
