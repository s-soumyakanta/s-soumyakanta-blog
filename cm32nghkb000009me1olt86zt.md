---
title: "How to Set Up Shadcn UI with Next.js 15 and React 19"
seoTitle: "Setting Up Shadcn UI in Next.js 15"
seoDescription: "Learn to install Shadcn UI with Next.js 15 and React 19 using `npx --force` to resolve dependency conflicts effectively"
datePublished: Mon Nov 04 2024 06:38:09 GMT+0000 (Coordinated Universal Time)
cuid: cm32nghkb000009me1olt86zt
slug: how-to-set-up-shadcn-ui-with-nextjs-15-and-react-19
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1730702264086/19da48d6-4d1a-4f08-9d38-888222d1ca15.png
tags: nextjs

---

In this blog post, I'll explain how I solved the dependency issues I faced while installing Shadcn UI in my Next.js 15 application, especially when using React 19. If you've had similar problems, this guide will show you how to use the `npx --force` command effectively.

## The Challenge

Recently, I created a new Next.js 15 application and was excited to add Shadcn UI for its rich set of components. However, when I tried to install Shadcn UI using the usual method, I ran into unresolved dependency conflicts. The error message showed that some packages needed specific versions of React that didn't work with React 19.

### Understanding Peer Dependencies

In the npm ecosystem, peer dependencies let a package specify that it works with a specific version of another package. When you install a package, npm checks these peer dependencies to ensure they are compatible. If there's a mismatch, npm will show an error, which is what happened in my case.

## The Solution: Using `npx --force`

After encountering the dependency errors, I researched possible solutions and found that I could bypass these conflicts by using the `--force` option with the `npx` command. This option forces the installation to continue, ignoring any dependency warnings.

### How to Use `npx --force`

Here’s how I resolved the issue using `npx --force`:

1. **Open your terminal**: Navigate to your Next.js project directory.
    
2. **Run the initialization command with** `--force`:
    
    ```bash
    npx --force shadcn@latest init -d
    ```
    

By using the `--force` flag with the `npx` command, I told npm to continue with the installation, ignoring any peer dependency warnings that might have come up due to using React 19.

## Verifying the Installation

After using `npx --force`, I checked my `package.json` file to confirm that Shadcn UI was listed under dependencies. To ensure everything was set up correctly, I ran the development server with:

```bash
npm run dev
```

This allowed me to verify that the Shadcn components were working seamlessly in my Next.js application.

## Conclusion

Using `npx --force` is an effective way to fix dependency issues, especially when dealing with packages that might not fully support the latest versions of React or other libraries. If you face similar conflicts while installing Shadcn UI in your Next.js 15 application, feel free to use this command.

I hope this guide helps you overcome any installation challenges you might encounter. If you have any questions or extra tips, feel free to share them in the comments! Happy coding!